# TensorFlow Lite / LiteRT — Tooling ecosystem

- **Netron** — visualize `.tflite` graphs (same tool used for ONNX).
- **TensorFlow Lite Model Maker** — high-level API for transfer-learning common tasks (image classification, object detection) directly to `.tflite`.
- **MediaPipe Tasks** — pre-built, delegate-aware pipelines (vision, text, audio, and on-device LLM inference) built on top of LiteRT.
- **ML Kit** — Google's higher-level mobile SDK wrapping TFLite models for common vision/text tasks with minimal code.
- **`ai-edge-torch`** — Google's library for converting PyTorch models directly to LiteRT/TFLite, including quantization-aware export paths for on-device LLMs.
- **TFLite Benchmark Tool** (`benchmark_model`) — a command-line binary for measuring per-op latency and confirming which delegate actually executed each op.
- **`tflite_support`** — metadata/schema tooling for attaching labels, normalization params, and task type to a `.tflite` file so it's self-describing for ML Kit/Task Library consumers.
