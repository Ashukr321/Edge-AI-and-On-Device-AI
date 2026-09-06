# Mobile AI — Typical mobile AI features

- **Camera ML**: real-time object detection, scene segmentation, portrait-mode depth estimation, barcode/document scanning, OCR.
- **On-device translation**: offline language packs (Google Translate, Apple Translate) using compact seq2seq or transformer models cached locally.
- **Smart replies / text prediction**: keyboard suggestion models (Gboard, iOS predictive text) trained with federated learning in some cases.
- **Biometrics**: face/fingerprint matching pipelines that must run on-device for privacy and speed (embedding extraction plus on-device matching against a stored template — the template itself typically never leaves a secure enclave).
- **Voice**: wake-word detection, on-device speech-to-text for short commands, voice isolation/noise suppression during calls.
- **Generative features**: on-device small language models for summarization, smart reply, and writing assistance (Gemini Nano, Apple's on-device foundation model).
