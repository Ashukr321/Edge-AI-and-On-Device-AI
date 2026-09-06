# Edge AI Fundamentals — Typical hardware tiers

| Tier | Examples | Power | Typical models |
|---|---|---|---|
| MCU / TinyML | ARM Cortex-M, ESP32 | mW | Tiny CNNs/DNNs, KB-scale, keyword spotting |
| Mobile SoC | Apple A/M-series, Snapdragon, Exynos, Google Tensor | ~1–5 W | MobileNet/EfficientNet-class CNNs, small transformers |
| Edge GPU/accelerator boards | NVIDIA Jetson (Orin/Xavier), Google Coral (Edge TPU), Intel Movidius/NPU | 5–60 W | YOLO-class detectors, segmentation, speech models |
| Edge servers/gateways | Industrial PCs, on-prem GPU boxes | 100s W | Larger vision/NLP models, multi-stream video analytics |
