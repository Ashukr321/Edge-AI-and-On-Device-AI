# Browser AI: Running Machine Learning Client-Side — Key concepts

| Concept | Description |
|---|---|
| Model format | ONNX, TensorFlow.js graph/layers format, or custom GGUF (for llama.cpp-style runtimes) |
| Backend | The compute engine actually running ops: WASM, WebGL, WebGPU, or a native OS API |
| Quantization | Reducing weights to int8/int4 or fp16 to shrink download size and speed up inference |
| Model caching | Using Cache API / IndexedDB so the (large) model is downloaded once and reused across sessions |
| Streaming/progressive load | Loading model shards as they arrive rather than waiting for the whole file |
| Warm-up | First inference is often slow (shader compilation, JIT); subsequent calls are faster |
