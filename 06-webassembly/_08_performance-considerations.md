# WebAssembly (WASM) for Edge & On-Device AI — Performance considerations

- **Enable SIMD and threads** wherever the target supports them — the difference for matmul-heavy ML workloads is substantial (often multiple times faster than scalar, single-threaded WASM).
- **Threads require cross-origin isolation** in browsers (`Cross-Origin-Opener-Policy`/`Cross-Origin-Embedder-Policy` headers) because they rely on `SharedArrayBuffer`, which browsers restrict post-Spectre.
- **Memory growth has a cost**: linear memory grows in fixed-size pages and reallocation can stall; pre-size buffers where the model size is known.
- **Quantize models** (int8/int4) — CPU/WASM inference benefits enormously since it reduces both memory bandwidth and the arithmetic per op.
- **Startup/instantiation cost**: larger WASM binaries take longer to compile/instantiate; streaming compilation (`WebAssembly.instantiateStreaming`) overlaps download and compile.
