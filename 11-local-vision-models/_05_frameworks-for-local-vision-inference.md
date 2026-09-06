# Local Vision Models — Frameworks for local vision inference

- **TensorFlow Lite (LiteRT)** — Google's mobile/embedded runtime; ships with delegates for NNAPI (Android), Core ML (iOS), GPU, and Hexagon; the long-time standard for mobile CV.
- **ONNX Runtime (with Execution Providers)** — cross-platform runtime that runs ONNX-exported models with hardware-specific execution providers (CUDA, TensorRT, CoreML, NNAPI, DirectML, OpenVINO).
- **Core ML** (Apple) — native runtime for iOS/macOS, automatically leverages the Apple Neural Engine; models are converted via `coremltools`.
- **MediaPipe** (Google) — a task-oriented framework (Tasks API) providing ready-made pipelines for detection, segmentation, pose, hand tracking, etc., across Android, iOS, web, and desktop with a consistent API.
- **NCNN / MNN** — lightweight C++ inference frameworks (Tencent/Alibaba) popular in mobile production apps for their small binary size and speed.
- **OpenVINO** (Intel) — optimizes and runs models on Intel CPUs/iGPUs/VPUs, common in industrial and desktop edge deployments.
