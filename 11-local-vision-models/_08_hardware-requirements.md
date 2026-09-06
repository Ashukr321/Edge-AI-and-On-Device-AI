# Local Vision Models — Hardware requirements

| Task | Typical model size | Hardware |
|---|---|---|
| Classification/detection (nano/lite) | 1-10M params | Phone CPU/NPU, Raspberry Pi 4/5, microcontroller-class (with further shrinkage) |
| Segmentation/pose (MediaPipe-class) | 1-10M params | Phone CPU/GPU, runs comfortably at 30 FPS on modern phones |
| Small VLM (Moondream, SmolVLM) | 0.25-2B params | 4-8 GB RAM, phone-class NPU/GPU or laptop CPU |
| LLaVA-class VLM (7B backbone) | ~7B params | Laptop/desktop GPU with 8GB+ VRAM, or quantized CPU inference |
