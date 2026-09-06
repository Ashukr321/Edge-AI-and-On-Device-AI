# Browser AI: Running Machine Learning Client-Side — Performance considerations

- **Quantize aggressively** (int8/int4) to cut download size and often speed up WASM/CPU inference; watch for accuracy loss on smaller models.
- **Pick the right backend per device**: WebGPU generally wins for larger models with heavy matmuls when available; WASM+SIMD+threads is the safe universal fallback; WebGL is legacy but still broadly supported.
- **Cache the model** in the Cache API / IndexedDB (or an Origin Private File System) so users don't re-download on every visit.
- **Off-main-thread execution**: run inference in a Web Worker to keep the UI responsive; TensorFlow.js, ONNX Runtime Web, and Transformers.js all support worker usage.
- **Warm-up pass**: run a dummy inference at load time to trigger shader/kernel compilation before the user's first real request.
- **Memory ceiling**: mobile browsers impose tab memory limits; multi-GB LLMs may crash on low-RAM devices — always feature-detect and offer a smaller model fallback.
