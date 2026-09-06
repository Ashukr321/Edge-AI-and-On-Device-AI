# Android Edge AI — Model formats / deployment workflow

1. Train in PyTorch/TensorFlow.
2. Convert to `.tflite` (LiteRT converter) or export to ONNX/ExecuTorch `.pte` if using those runtimes.
3. Quantize (dynamic range, full-integer, or QAT) — INT8 is the common target for CPU/DSP paths.
4. Bundle under `app/src/main/assets/` for small models, or configure as a **Play Feature Delivery** on-demand/conditional module for larger ones so the base APK stays under size limits.
5. Load via `Interpreter` (LiteRT), `ML Kit` custom-model APIs, or `OrtSession` (ONNX Runtime), specifying delegate preference order.
6. Instrument with Android's GPU/NNAPI profiling tools and `adb`-based benchmarking (LiteRT's `benchmark_model` tool) before release.
