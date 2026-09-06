# WebAssembly (WASM) for Edge & On-Device AI — Conceptual build flow: C/C++ → WASM (Emscripten)

```bash
# Typical pattern used by ONNX Runtime Web / llama.cpp / whisper.cpp build scripts
emcc inference.cpp -O3 \
  -msimd128 \                 # enable WASM SIMD
  -pthread \                  # enable WASM threads (needs cross-origin isolation in the browser)
  -s WASM=1 \
  -s ALLOW_MEMORY_GROWTH=1 \
  -o inference.js             # emits inference.wasm + a JS loader/glue file
```

The resulting `.wasm` + glue JS is then loaded like any other module — the same output shape ONNX Runtime Web and TensorFlow.js ship internally.
