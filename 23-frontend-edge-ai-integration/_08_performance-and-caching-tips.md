# Performance & Caching Tips

- **Always run inference in a Web Worker** — model load and forward passes are synchronous CPU/GPU work that will jank the UI thread otherwise.
- **Pick the smallest model that meets your accuracy bar.** A quantized/distilled variant (`-tiny`, `-small`, int8) often costs 4-10x less download and 2-4x less inference time for a small accuracy drop — see [Model Quantization](../08-model-quantization/) and [Model Compression](../09-model-compression/).
- **Lazy-load the model** — only start the `pipeline()`/model download when the feature is actually used (e.g. on first interaction), not on initial page load.
- **Feature-detect before choosing a backend/model size**: check `navigator.gpu` for WebGPU, `navigator.deviceMemory` / `navigator.hardwareConcurrency` for a rough capability signal, and offer a lighter model or a cloud fallback on weak devices.
- **Show progress during model download** — most runtimes expose a progress callback; a multi-MB download with no feedback reads as a frozen app.
- **Reuse a single loaded pipeline/model instance** across calls (see `classifier ??= ...` pattern above) — re-initializing per-call reloads weights every time.
