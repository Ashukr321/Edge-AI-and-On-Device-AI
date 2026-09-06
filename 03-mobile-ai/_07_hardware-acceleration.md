# Mobile AI — Hardware acceleration

Mobile SoCs expose several compute backends that a delegate/execution-provider chooses among at runtime:

- **CPU** — always available, used as a fallback; libraries like XNNPACK optimize CPU kernels specifically for mobile ARM cores.
- **GPU** — good throughput for parallel, regular workloads (e.g., image models); accessed via OpenGL/Vulkan (Android) or Metal (iOS).
- **DSP/NPU** — dedicated low-power neural accelerators (Qualcomm Hexagon, MediaTek APU, Apple Neural Engine, Google Tensor's TPU-derived core); best power efficiency for supported ops, but with the narrowest operator coverage.
- Runtime frameworks generally let you specify a preference order and fall back automatically when a backend can't run part of the graph.
