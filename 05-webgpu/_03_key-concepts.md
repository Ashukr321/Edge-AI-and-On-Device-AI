# WebGPU for Machine Learning — Key concepts

| Concept | Description |
|---|---|
| `GPUAdapter` | Represents a physical/logical GPU the browser can use |
| `GPUDevice` | The logical connection to the adapter; used to create all other GPU resources |
| `GPUBuffer` | Linear memory on the GPU (vertex, uniform, or storage buffers) |
| `GPUShaderModule` | Compiled WGSL shader code |
| `GPUComputePipeline` | A pipeline binding a compute shader entry point plus its bind group layout |
| `GPUBindGroup` | The actual resource bindings (buffers/textures/samplers) passed to a pipeline |
| `GPUCommandEncoder` | Records commands (dispatches, copies) into a `GPUCommandBuffer` |
| Workgroup | A group of GPU threads executing the same compute shader invocation, sized via `@workgroup_size` in WGSL |
| WGSL | WebGPU Shading Language — the (Rust-like syntax) shader language WebGPU requires, replacing GLSL |
