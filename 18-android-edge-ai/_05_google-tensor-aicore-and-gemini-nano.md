# Android Edge AI — Google Tensor, AICore, and Gemini Nano

Google's Tensor SoC (Pixel 6 onward) integrates a custom TPU-derived core alongside CPU/GPU, giving Pixel devices a consistent, well-supported acceleration target that Google tunes directly (useful for camera computational-photography features, on-device speech recognition, and Gemini Nano inference). AICore is the system service that loads and serves Gemini Nano so that:

- The model is downloaded/updated once per device rather than per app.
- Apps access it through ML Kit's GenAI APIs (summarization, rewriting, proofreading, image description) or lower-level prompting APIs, without bundling multi-gigabyte weights themselves.
- Availability is gated by device (Pixel and select partner devices with sufficient RAM/NPU) — apps must check availability and handle the fallback path (cloud model or feature disabled) on unsupported devices.
