# On-Device AI — On-device inference engines

- **Core ML** (Apple) — compiles models to run across CPU/GPU/ANE on
  iOS/macOS; models authored via `coremltools` conversion from PyTorch/TF.
- **TensorFlow Lite / LiteRT** (Google) — the standard cross-platform
  mobile/embedded runtime, with delegates for GPU, NNAPI, Hexagon, Core ML.
- **ONNX Runtime Mobile** — cross-platform, with execution providers for
  NNAPI, Core ML, QNN.
- **MediaPipe** (Google) — higher-level on-device pipelines for vision/
  audio tasks (face mesh, pose, hand tracking, on-device LLM via
  MediaPipe LLM Inference API).
- **llama.cpp / MLC-LLM / ExecuTorch** — increasingly used to run small
  quantized LLMs directly on phones and laptops (see `22-edge-ai-projects`
  for hands-on examples).
- **PyTorch ExecuTorch** — Meta's runtime purpose-built for on-device
  PyTorch model deployment across mobile and embedded targets.
