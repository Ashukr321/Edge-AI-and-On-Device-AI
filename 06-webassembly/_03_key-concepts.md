# WebAssembly (WASM) for Edge & On-Device AI — Key concepts

| Concept | Description |
|---|---|
| Linear memory | A single contiguous, resizable `ArrayBuffer`-backed memory space the WASM module operates on |
| SIMD (`wasm-simd`) | 128-bit vectorized instructions (`v128`) for parallel arithmetic — critical for matmul/convolution throughput |
| Threads (`wasm-threads`) | Shared-memory multithreading via `SharedArrayBuffer` + Web Workers, enabling multi-core inference |
| WASI | WebAssembly System Interface — a standardized syscall-like API (files, clocks, sockets) for running WASM **outside** the browser |
| Component Model | An emerging WASM standard for composing modules across languages with typed interfaces (WIT), relevant to portable edge-function deployment |
| AOT/JIT compilation | Browsers and standalone runtimes compile WASM to native machine code either ahead-of-time or on first execution |
