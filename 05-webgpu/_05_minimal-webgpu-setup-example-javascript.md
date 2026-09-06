# WebGPU for Machine Learning — Minimal WebGPU setup example (JavaScript)

```js
async function initWebGPU() {
  if (!navigator.gpu) throw new Error('WebGPU not supported in this browser');

  const adapter = await navigator.gpu.requestAdapter();
  if (!adapter) throw new Error('No GPUAdapter found');

  const device = await adapter.requestDevice();
  return device;
}
```
