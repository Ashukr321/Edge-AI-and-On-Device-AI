# WebAssembly (WASM) for Edge & On-Device AI — Why WASM for ML

- **Reuse native code**: ONNX Runtime, TensorFlow Lite kernels, and llama.cpp are written in C/C++; compiling to WASM avoids rewriting them in JS.
- **Near-native CPU performance**: WASM is a low-level, statically-typed bytecode designed for fast JIT/AOT compilation — typically 1.5–3x slower than native, far faster than interpreted JS for numeric code.
- **Portability**: one `.wasm` binary runs identically across OS/CPU architecture, in-browser or out, given a compliant runtime.
- **Sandboxing**: WASM's memory model (linear memory, no arbitrary pointers into host memory) makes it safe to run untrusted or third-party model code.
- **Universal fallback**: works on every browser and device, including those without WebGPU/WebGL support — the safety net backend.
