# Mobile AI — Performance & optimization tips

- Profile on real mid-range devices, not just the flagship you own — the median user's phone is 2-4 years older and thermally worse.
- Prefer INT8 quantization for CPU/DSP paths; measure accuracy drop against a held-out set before shipping.
- Batch size 1 is the mobile norm — optimize for single-inference latency, not throughput.
- Warm up delegates/interpreters once at app start (or session start) rather than per-call; backend initialization can dominate the first inference.
- Avoid unnecessary CPU↔GPU/NPU memory copies; keep pre/post-processing (resize, normalize) as cheap and vectorized as possible.
- Cap inference frequency on continuous streams (e.g., every 3rd camera frame) rather than every frame, when the UX tolerates it.
- Watch for thermal throttling in long sessions; some apps deliberately downshift model size or frame rate after sustained use.
- Use each platform's model-analysis tooling (LiteRT's benchmark tool, Xcode Instruments, Android GPU/NNAPI profilers) before assuming a bottleneck.
