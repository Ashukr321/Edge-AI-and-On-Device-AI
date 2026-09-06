# Local Vision Models — Popular models

### Classification / backbones
- **MobileNetV2/V3** (Google) — depthwise-separable CNNs, a few million parameters, the long-standing default for on-device classification.
- **EfficientNet-Lite** — scaled family balancing accuracy and latency for mobile.

### Object detection
- **YOLOv8n / YOLOv10n / YOLO11n** (Ultralytics) — "nano" variants at roughly 2-3M parameters designed for edge/mobile real-time detection; larger s/m/l/x variants trade speed for accuracy.
- **EfficientDet-Lite** (Google) — scalable detector family (D0-D4) tuned for edge deployment via TFLite.
- **MediaPipe Object Detector** — pre-packaged, MediaPipe-optimized detection models (often EfficientDet-based) ready to drop into mobile/web apps.

### Segmentation & pose
- **MediaPipe Selfie Segmentation, Pose, Hands, Face Mesh** — Google's task-specific solutions, heavily optimized for real-time mobile use (background blur, AR filters, fitness apps).
- **MobileSAM / EdgeSAM** — distilled, lightweight variants of Segment Anything (SAM) aimed at real-time interactive segmentation on-device.

### On-device vision-language models
- **Moondream** (Moondream AI) — a very small (~1.6B-2B) open VLM built specifically for edge captioning/VQA use cases.
- **SmolVLM** (Hugging Face) — a family of small VLMs (256M-2.2B) explicitly designed for on-device/browser deployment.
- **LLaVA small variants** (e.g. LLaVA-1.5/1.6 with a 7B LLM backbone, or community "tiny-llava" builds on 1-3B backbones) — general-purpose visual question answering; the 7B versions need laptop-class hardware, not phone-class.
- **Apple/Google on-device multimodal features** — iOS/Android system-level visual intelligence (e.g. on-device photo search, live text) built on proprietary compact vision encoders, not directly user-downloadable as standalone models.
