# WebGPU for Machine Learning — How frameworks use WebGPU

- **TensorFlow.js WebGPU backend** (`@tensorflow/tfjs-backend-webgpu`) — reimplements TF.js kernels as WGSL compute shaders; generally the fastest TF.js backend on supported hardware for medium/large models, selectable via `tf.setBackend('webgpu')`.
- **ONNX Runtime Web WebGPU Execution Provider** — runs ONNX graphs with ops dispatched to WebGPU compute shaders, with automatic fallback to WASM for unsupported ops; used by Transformers.js under the hood when `device: 'webgpu'` is requested.
- **WebLLM / MLC-LLM** — an entire LLM inference engine (attention, KV-cache, quantized matmuls) built directly on WebGPU compute shaders via the MLC (Machine Learning Compilation) TVM-based compiler stack, enabling multi-billion-parameter model inference in-browser.
- **wgpu / Dawn** — the two major native implementations of the WebGPU spec (wgpu in Rust from the Firefox/Servo ecosystem; Dawn in C++ from Google/Chromium) — both also usable outside the browser (e.g., in native Rust or C++ apps, or via `wgpu-py`), making WebGPU a portable GPU API beyond just web pages.
