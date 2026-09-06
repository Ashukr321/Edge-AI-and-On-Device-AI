# WebAssembly (WASM) for Edge & On-Device AI — Overview

WebAssembly is a portable, binary instruction format designed as a compilation target for languages like C, C++, and Rust. It runs in a sandboxed, near-native-speed virtual machine — originally built into browsers, but now also standalone via runtimes like Wasmtime and Wasmer. For ML at the edge, WASM matters because it lets existing native inference code (tensor libraries written in C/C++/Rust) run **unmodified in a browser** or in **any WASM-capable edge runtime**, without a native binary per OS/architecture.

This makes WASM the "portable compute" counterpart to WebGPU's "portable GPU" — where WebGPU targets the GPU, WASM targets CPU-bound, sandboxed, cross-platform execution of native code.
