# WebGPU for Machine Learning — Why WebGPU matters for ML

WebGL was designed for rendering triangles, not matrix multiplication. Getting a matmul or convolution to run on WebGL meant encoding tensors as textures and computing via fragment shaders — workable, but with real overhead and awkward precision/data-type limitations (no native int8/int32 storage buffers, limited to texture formats). WebGPU instead offers:

- **Native compute shaders** written in WGSL, dispatched over a 3D grid of workgroups, operating directly on storage buffers (arbitrary structured data, not texel-packed workarounds).
- **Lower CPU overhead** per draw/dispatch call versus WebGL, via pre-built, immutable pipeline state objects and command buffers/encoders.
- **Better numeric support** — storage buffers can hold `f32`, `i32`, `u32`, `f16` (with the `shader-f16` feature) directly.
- **Explicit memory & synchronization model**, letting frameworks fuse kernels and manage buffer lifetimes more efficiently than WebGL's implicit state machine.
