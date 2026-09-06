# WebAssembly (WASM) for Edge & On-Device AI — Trade-offs vs. native and vs. WebGPU

| Dimension | WASM | Native binary | WebGPU |
|---|---|---|---|
| Portability | Very high — one binary, sandboxed, browser + WASI runtimes | Low — per-OS/arch builds | High in-browser, but GPU/driver dependent |
| Raw performance | Near-native for CPU work (~1.5–3x native, workload-dependent) | Fastest (no sandbox overhead) | Fastest for large parallel/matmul workloads on a capable GPU |
| Hardware requirement | None — runs on any CPU | Depends on target | Requires a WebGPU-capable GPU/driver |
| Security | Strong sandboxing by design | Full OS access, no sandbox | Sandboxed, GPU-side |
| Best fit | CPU inference fallback, portable edge functions, reusing existing C/C++/Rust ML code | Maximum performance when portability doesn't matter | Large models / heavy compute where a capable GPU is present |

In short: reach for WASM as the reliable, portable, CPU-bound baseline that runs everywhere (and reuses existing native codebases); reach for WebGPU when a capable GPU is available and the workload is compute-heavy enough to benefit; fall back to native only when you control the deployment target completely and portability doesn't matter.
