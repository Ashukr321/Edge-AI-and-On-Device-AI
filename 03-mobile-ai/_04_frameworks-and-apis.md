# Mobile AI — Frameworks & APIs

| Framework | Maintainer | Platforms | Notes |
|---|---|---|---|
| TensorFlow Lite / **LiteRT** | Google | Android, iOS, embedded Linux | Renamed to LiteRT in 2024; `.tflite` FlatBuffer format; broad delegate ecosystem (GPU, NNAPI, Core ML, XNNPACK, Hexagon). |
| ONNX Runtime Mobile | Microsoft / ONNX community | Android, iOS | Runs ONNX models with a reduced-size mobile build; supports NNAPI and Core ML execution providers; good choice when the training pipeline is already ONNX-centric. |
| PyTorch Mobile → **ExecuTorch** | Meta (PyTorch) | Android, iOS, embedded | PyTorch Mobile is in maintenance/legacy mode; ExecuTorch is its actively developed successor, purpose-built for edge/mobile with ahead-of-time compilation and backend delegates (XNNPACK, Core ML, Vulkan, Qualcomm QNN). |
| **MediaPipe** (MediaPipe Tasks / Solutions) | Google | Android, iOS, web, desktop | High-level, ready-made pipelines for vision, audio, and text (face mesh, pose, hand tracking, gesture recognition, LLM Inference API) built on top of TFLite/LiteRT. |
| Core ML | Apple | iOS, macOS | Apple's native inference framework; see `19-ios-edge-ai`. |
| ML Kit | Google | Android, iOS | High-level SDK for common vision/text/genAI tasks, backed by TFLite or cloud depending on the API. |

Choosing among these usually comes down to: what framework the model was trained in, whether you need to target both platforms with one artifact (ONNX Runtime or LiteRT via conversion), and whether a ready-made high-level API (MediaPipe/ML Kit) already covers the feature.
