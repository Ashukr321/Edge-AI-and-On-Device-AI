# Browser AI: Running Machine Learning Client-Side — Code example: running an ONNX model directly with ONNX Runtime Web

```js
import * as ort from 'onnxruntime-web/webgpu';

const session = await ort.InferenceSession.create('model.onnx', {
  executionProviders: ['webgpu', 'wasm'], // fall back to wasm if webgpu unavailable
});

const inputTensor = new ort.Tensor('float32', inputData, [1, 3, 224, 224]);
const results = await session.run({ input: inputTensor });
console.log(results.output.data);
```
