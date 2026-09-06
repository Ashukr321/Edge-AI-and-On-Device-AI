# TensorFlow Lite / LiteRT — Delegates for hardware acceleration

| Delegate | Platform / Hardware | Notes |
|---|---|---|
| **XNNPACK** | CPU (all platforms) | Optimized floating-point/quantized CPU kernel library; now the *default* backend for float32 CPU inference in TFLite, not just an opt-in delegate. |
| **GPU delegate** | Android & iOS GPUs | Uses OpenGL ES/OpenCL/Vulkan on Android and Metal on iOS; good for float16/float32 models with regular conv/matmul-heavy graphs. |
| **NNAPI delegate** | Android | Routes ops to whatever accelerator the Android Neural Networks API exposes (vendor DSP/NPU/GPU). Deprecated for new vendor work since Android 15 in favor of direct vendor delegates, but still broadly present. |
| **Hexagon delegate** | Qualcomm Snapdragon DSP | Targets older Qualcomm DSPs directly, predating broad NNAPI/QNN adoption; still used on some embedded Qualcomm targets. |
| **Core ML delegate** | iOS / macOS | Hands the graph to Apple's Core ML stack, enabling Neural Engine acceleration on Apple Silicon devices. |
| **EdgeTPU delegate** | Google Coral (Edge TPU) | For USB/PCIe Coral accelerators; requires a specifically compiled, fully-INT8-quantized model. |

Delegation is partial: unsupported ops silently fall back to CPU, so profiling (see below) is important to confirm a delegate is actually accelerating the intended layers.
