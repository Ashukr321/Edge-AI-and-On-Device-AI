# ONNX & ONNX Runtime — Trade-offs

**Strengths**
- Framework-neutral: train anywhere, deploy anywhere ORT (or another ONNX-compatible runtime) runs.
- One of the broadest hardware-backend matrices of any inference engine (CPU/GPU/NPU/mobile/browser).
- Mature quantization and graph-optimization tooling.
- Strong ecosystem: HuggingFace Optimum, Olive, and many MLOps platforms treat ONNX as a first-class export target.

**Weaknesses**
- Export is not always lossless: dynamic control flow, custom autograd functions, and some ops (especially in bleeding-edge research models) can fail to trace or require custom op registration.
- Opset drift — a model exported at a high opset may not load on an older ORT version, and vice versa.
- Not every EP supports every operator; silent CPU fallback for unsupported nodes can quietly erase expected GPU/NPU speedups if not checked via profiling.
- Debugging a broken export (shape mismatch, wrong output) usually requires visual graph inspection (Netron) rather than being obvious from the export call itself.
- Compared to vendor-native formats (Core ML, TFLite), ORT sometimes trails on device-specific NPU utilization until an EP matures.
