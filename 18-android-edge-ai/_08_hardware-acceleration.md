# Android Edge AI — Hardware acceleration

- **CPU**: XNNPACK-backed kernels, always available; use `setNumThreads` to tune.
- **GPU**: OpenGL/Vulkan-based delegate, good for image/vision models with regular compute patterns.
- **NNAPI delegate**: routes to whatever NPU/DSP the device exposes through the system API; being phased out for new development in favor of:
- **Vendor delegates**: Qualcomm's QNN/SNPE-based delegate for Hexagon NPUs, MediaTek's NeuroPilot delegate for APUs — direct access to chipset-specific acceleration and newer ops.
- **Google Tensor**: Pixel-specific tuning; some features route through AICore rather than a raw delegate.
