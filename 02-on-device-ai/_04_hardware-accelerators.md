# On-Device AI — Hardware accelerators

| Platform | Accelerator | Notes |
|---|---|---|
| Apple (iOS/macOS) | Apple Neural Engine (ANE) | Exposed via Core ML; automatic op dispatch across CPU/GPU/ANE |
| Qualcomm Snapdragon | Hexagon DSP/NPU | Exposed via QNN SDK / SNPE, and Android NNAPI |
| Google Pixel | Google Tensor (TPU-derived) | Used for on-device Assistant, call screening, photo processing |
| ARM-based SoCs | Ethos-U/Ethos-N NPU | Targets microcontroller and mobile-class ARM designs |
| Samsung Exynos | Exynos NPU | Used for on-device camera/vision features |
| Generic Android | NNAPI (deprecated in newer Android in favor of vendor drivers) | Abstraction layer routing to whichever NPU/DSP is present |

Most of these accelerators are optimized for INT8 (and increasingly INT4)
matrix-multiply-heavy workloads (convolutions, transformer attention/FFN
blocks) and are far more power-efficient per operation than running the
same model on the CPU.
