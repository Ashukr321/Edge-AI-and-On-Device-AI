# WebGPU for Machine Learning — Performance: WebGPU vs. WebGL vs. WASM (qualitative)

| Backend | Strengths | Weaknesses |
|---|---|---|
| **WebGPU** | Native compute shaders, best raw throughput for large matmuls/convolutions on capable GPUs, lower per-dispatch overhead, supports large LLM inference | Newer/less universally supported; driver quality still maturing on some platforms; shader compilation ("pipeline creation") adds first-run latency |
| **WebGL** | Very broadly supported (works on essentially all browsers/devices), mature | GPGPU via textures is inefficient; no true compute shaders; overhead from texture packing/unpacking; effectively legacy for new ML work |
| **WASM (CPU)** | Universal fallback, deterministic, works with no GPU at all, great with SIMD+threads for small/medium models | CPU throughput ceiling is far below GPU for large models; battery/thermal cost on sustained heavy inference |

In practice: WebGPU tends to substantially outperform WebGL for compute-heavy workloads and often outperforms WASM once a model is large enough to be GPU-bound rather than dispatch-overhead-bound; for small models or on GPU-constrained devices, WASM can still win due to WebGPU's shader compile/warm-up cost.
