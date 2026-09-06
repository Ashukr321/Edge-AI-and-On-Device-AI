# Android Edge AI — Key concepts

- **Fragmentation**: Android runs on SoCs from Qualcomm (Snapdragon/Hexagon), MediaTek (Dimensity/APU), Samsung (Exynos), Google (Tensor), and others — each with different NPU/DSP hardware and driver quality. Code that "just works" on a Pixel may silently fall back to CPU on a mid-range device.
- **Delegate model**: LiteRT (and ML Kit under the hood) picks an execution backend — CPU, GPU, NNAPI, or a vendor-specific delegate — at runtime, so one model file can target multiple backends.
- **Vendor driver APIs replacing NNAPI**: Google has been deprecating NNAPI for app developers in favor of frameworks talking directly to vendor-supplied acceleration stacks (e.g., Qualcomm's QNN/SNPE, MediaTek's NeuroPilot) via LiteRT delegates, giving access to newer chipset features NNAPI's frozen API surface can't expose.
- **AICore**: a system service (introduced with Android 14 on Pixel, expanding to more OEM devices) that hosts Gemini Nano and manages model updates, memory, and security independent of individual apps — apps call it rather than bundling the LLM themselves.
- **Play Feature Delivery**: Google Play's mechanism for splitting an app into base + on-demand modules, used to keep large ML models out of the initial install.
