# ONNX & ONNX Runtime — Execution Providers

ORT's defining feature is that the same `.onnx` file runs across wildly different hardware by swapping EPs — the application code barely changes.

| Execution Provider | Target | Notes |
|---|---|---|
| **CPUExecutionProvider** | Any CPU | Default, always available fallback. Uses oneDNN/MLAS kernels internally. |
| **CUDAExecutionProvider** | NVIDIA GPUs | Standard GPU acceleration via cuDNN/cuBLAS. |
| **TensorrtExecutionProvider** | NVIDIA GPUs (Jetson, datacenter) | Compiles subgraphs into TensorRT engines for lower latency; best for static/known shapes. |
| **DmlExecutionProvider (DirectML)** | Any DirectX 12 GPU on Windows | Vendor-agnostic (AMD/Intel/NVIDIA) GPU acceleration on Windows. |
| **CoreMLExecutionProvider** | Apple Silicon / iOS-macOS | Delegates ops to Core ML, which in turn can use the Apple Neural Engine. |
| **NnapiExecutionProvider** | Android | Delegates to Android Neural Networks API for vendor NPU/DSP/GPU acceleration (NNAPI is deprecated on newer Android in favor of vendor-specific paths, but still widely used). |
| **QNNExecutionProvider** | Qualcomm Snapdragon (Hexagon NPU) | Common on-device path for Snapdragon laptops/phones. |
| **OpenVINOExecutionProvider** | Intel CPU/iGPU/VPU | Intel's inference toolkit as a backend. |
| **WebGPU EP / WASM (JS)** | Browsers | `onnxruntime-web` runs models client-side via WebAssembly (CPU) or the WebGPU EP for GPU acceleration in-browser. |
| **ROCm/MIGraphX** | AMD GPUs | AMD's GPU compute stack. |

EPs are tried in a priority order you specify; ORT falls back to CPU for any node an EP can't execute, so a graph can be split across multiple providers transparently.
