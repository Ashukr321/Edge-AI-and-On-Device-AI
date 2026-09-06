# WebGPU for Machine Learning — Minimal compute shader example (WGSL): element-wise vector add

```wgsl
@group(0) @binding(0) var<storage, read> a: array<f32>;
@group(0) @binding(1) var<storage, read> b: array<f32>;
@group(0) @binding(2) var<storage, read_write> result: array<f32>;

@compute @workgroup_size(64)
fn main(@builtin(global_invocation_id) id: vec3<u32>) {
  let i = id.x;
  if (i < arrayLength(&result)) {
    result[i] = a[i] + b[i];
  }
}
```

```js
// Dispatching the shader above (device from initWebGPU())
const shaderModule = device.createShaderModule({ code: wgslCode });

const pipeline = device.createComputePipeline({
  layout: 'auto',
  compute: { module: shaderModule, entryPoint: 'main' },
});

const bindGroup = device.createBindGroup({
  layout: pipeline.getBindGroupLayout(0),
  entries: [
    { binding: 0, resource: { buffer: bufferA } },
    { binding: 1, resource: { buffer: bufferB } },
    { binding: 2, resource: { buffer: bufferResult } },
  ],
});

const encoder = device.createCommandEncoder();
const pass = encoder.beginComputePass();
pass.setPipeline(pipeline);
pass.setBindGroup(0, bindGroup);
pass.dispatchWorkgroups(Math.ceil(vectorLength / 64));
pass.end();

device.queue.submit([encoder.finish()]);
```
