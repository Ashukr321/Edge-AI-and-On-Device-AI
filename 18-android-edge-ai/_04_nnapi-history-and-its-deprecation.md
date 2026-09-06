# Android Edge AI — NNAPI history and its deprecation

NNAPI shipped in Android 8.1 as the standard way for higher-level frameworks (TFLite, ONNX Runtime, vendor SDKs) to reach GPU/DSP/NPU acceleration without each framework writing per-vendor drivers. Over subsequent Android releases it gained more op support and quantization options. However:

- Its API surface is frozen as of Android 15 — Google has stated it will not add new functionality to NNAPI going forward.
- The recommended path for accessing new accelerator capabilities is now direct vendor delegate integration (e.g., Qualcomm and MediaTek delegates for LiteRT), which can expose newer ops, better quantization support, and vendor-specific tuning that NNAPI's stable-but-static API cannot.
- LiteRT still ships an NNAPI delegate for backward compatibility, but new projects targeting the latest chipset features are steered toward the vendor delegate route.
