# Code Example: Image Classifier (React + Transformers.js)

```jsx
// useClassifier.js — a worker-backed hook
import { useEffect, useRef, useState } from 'react';

export function useClassifier() {
  const worker = useRef(null);
  const [result, setResult] = useState(null);
  const [loading, setLoading] = useState(false);

  useEffect(() => {
    worker.current = new Worker(new URL('./classifier.worker.js', import.meta.url), { type: 'module' });
    worker.current.onmessage = (e) => { setResult(e.data); setLoading(false); };
    return () => worker.current.terminate();
  }, []);

  const classify = (imageUrl) => {
    setLoading(true);
    worker.current.postMessage({ imageUrl });
  };

  return { classify, result, loading };
}
```

```js
// classifier.worker.js
import { pipeline } from '@huggingface/transformers';

let classifier;
self.onmessage = async ({ data: { imageUrl } }) => {
  classifier ??= await pipeline('image-classification', 'Xenova/vit-base-patch16-224');
  const output = await classifier(imageUrl);
  self.postMessage(output);
};
```

```jsx
// App.jsx
import { useClassifier } from './useClassifier';

export default function App() {
  const { classify, result, loading } = useClassifier();

  return (
    <div>
      <input type="file" accept="image/*" onChange={(e) => {
        const url = URL.createObjectURL(e.target.files[0]);
        classify(url);
      }} />
      {loading && <p>Classifying...</p>}
      {result && <pre>{JSON.stringify(result, null, 2)}</pre>}
    </div>
  );
}
```

First run downloads ~90MB of model weights (cached after that); everything
runs on-device, no API key, no server.
