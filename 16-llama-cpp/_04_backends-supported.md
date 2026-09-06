# llama.cpp — Backends supported

- **CPU** — the baseline, with SIMD-optimized kernels (AVX2/AVX-512 on x86, NEON on ARM).
- **CUDA** — NVIDIA GPU acceleration, the most mature and fastest GPU backend.
- **Metal** — native acceleration on Apple Silicon (M-series), which pairs well with unified memory to run large models GPU-accelerated without discrete VRAM limits.
- **Vulkan** — cross-vendor GPU backend (AMD, Intel, NVIDIA) useful where CUDA isn't available.
- **SYCL** — Intel GPU backend (Arc, integrated Xe graphics) via oneAPI.
- **HIP/ROCm** — AMD GPU acceleration on Linux.

Only one backend is typically compiled in at a time (aside from CPU always being available as fallback), selected at build time via CMake flags.
