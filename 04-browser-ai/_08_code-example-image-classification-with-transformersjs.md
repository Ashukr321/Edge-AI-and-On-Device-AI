# Browser AI: Running Machine Learning Client-Side — Code example: image classification with Transformers.js

```js
import { pipeline } from '@huggingface/transformers';

// Loads a quantized ONNX model from the HF Hub, caches it via Cache API/IndexedDB
const classifier = await pipeline(
  'image-classification',
  'Xenova/vit-base-patch16-224',
  { dtype: 'q8' } // request an int8-quantized variant for smaller download / faster inference
);

const results = await classifier('https://example.com/cat.jpg');
console.log(results);
// [{ label: 'tabby cat', score: 0.94 }, ...]
```
