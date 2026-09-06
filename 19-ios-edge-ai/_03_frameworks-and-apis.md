# iOS Edge AI — Frameworks & APIs

| Framework | Purpose |
|---|---|
| **Core ML** | General-purpose model inference (classification, regression, embeddings, generative models); the common runtime underneath the higher-level frameworks below. |
| **Create ML** | App/tool (and Swift framework) for training or fine-tuning models directly on a Mac using templates for image classification, object detection, text classification, sound classification, tabular data, and recommendation, producing Core ML models directly. |
| **Vision** | High-level computer-vision APIs (face/landmark detection, text recognition/OCR, barcode detection, image saliency, trajectory/pose tracking) that wrap Core ML models Apple ships with the OS. |
| **Natural Language** | Tokenization, language identification, named entity recognition, and embedding APIs. |
| **Sound Analysis** | On-device audio/sound classification. |
| **Foundation Models framework** (iOS 18+/Apple Intelligence) | Swift API to prompt Apple's on-device LLM directly, with structured/guided generation and tool-calling support, for building generative features without server round-trips. |
| **coremltools** (Python) | Apple's conversion library for turning PyTorch/TensorFlow models into Core ML format. |
