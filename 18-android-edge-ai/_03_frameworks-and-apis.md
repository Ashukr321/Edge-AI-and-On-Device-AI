# Android Edge AI — Frameworks & APIs

| Layer | API/Framework | Purpose |
|---|---|---|
| High-level task APIs | **ML Kit** | Ready-made vision/text APIs: text recognition, barcode scanning, face detection, pose detection, on-device translation, smart reply, and (newer) **ML Kit GenAI APIs** — summarization, proofreading, image description — backed by Gemini Nano. |
| General inference runtime | **TensorFlow Lite / LiteRT** | Load and run custom `.tflite` models with CPU/GPU/NNAPI/vendor delegates. |
| Hardware abstraction (legacy) | **Android Neural Networks API (NNAPI)** | Introduced in Android 8.1 (API 27) as a system-level abstraction so frameworks could target any vendor's NPU/DSP through one interface. Google has since directed app developers away from NNAPI toward direct vendor delegates for new projects, though NNAPI remains present on-device for backward compatibility. |
| On-device GenAI | **AICore + Gemini Nano** | System-managed small language model exposed via ML Kit GenAI APIs and the (experimental) Gemini Nano AI Edge SDK for direct prompting. |
| Cross-platform alternative | **ONNX Runtime Mobile**, **ExecuTorch** | Same as covered in `03-mobile-ai`, both run on Android via their Android bindings/AARs. |
