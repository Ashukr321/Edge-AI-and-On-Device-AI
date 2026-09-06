# WebAssembly (WASM) for Edge & On-Device AI — Use in ML frameworks

- **ONNX Runtime Web (WASM backend)** — the default/fallback execution provider; the C++ ONNX Runtime core is compiled to WASM via Emscripten, optionally with SIMD and multi-threading enabled, giving reliable CPU inference in any browser.
- **TensorFlow.js WASM backend** (`@tensorflow/tfjs-backend-wasm`) — compiles the XNNPACK-based TF.js CPU kernels to WASM; often faster and more consistent than the plain JS backend, and a good middle ground when WebGL/WebGPU aren't ideal (e.g., small models, older devices).
- **llama.cpp → WASM** — the popular C/C++ LLM inference engine has been compiled to WASM (directly, and via projects/forks that target browser deployment), enabling quantized (GGUF) LLM inference client-side without any GPU dependency, at a real but tolerable CPU-throughput cost.
- **whisper.cpp → WASM** — the same pattern for speech-to-text (OpenAI Whisper inference in C++, browser demo built via Emscripten).
