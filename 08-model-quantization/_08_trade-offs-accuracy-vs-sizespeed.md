# Model Quantization — Trade-offs: accuracy vs. size/speed

| Precision | Size vs. FP32 | Typical accuracy impact | Notes |
|---|---|---|---|
| FP16 | 2x smaller | Usually negligible | Widely supported on GPUs/NPUs with native FP16 units |
| INT8 | 4x smaller | Small (often <1–2 pts) with good calibration or QAT | The practical default for edge/mobile inference |
| INT4 (weight-only, LLMs) | ~8x smaller | Noticeable but often acceptable with GPTQ/AWQ; larger models degrade less than small ones | Activations frequently kept at 8/16-bit; accuracy loss task-dependent |
| GGUF K-quants (Q4_K_M etc.) | Similar to INT4 range | Mixed precision per block improves perplexity vs. naive Q4_0 | Popular for running LLMs on consumer CPUs via llama.cpp |

General rules of thumb:
- Larger models tolerate aggressive quantization better than small ones (more redundancy to absorb error).
- Per-channel quantization and QAT both meaningfully reduce accuracy loss versus naive per-tensor PTQ, at the cost of engineering complexity or retraining time.
- Weight-only quantization (common for LLMs) preserves more accuracy than quantizing both weights and activations, at less memory savings since activations stay at higher precision during compute.
- Below INT4, the accuracy cliff steepens quickly for most models without careful per-channel/group-wise scaling (e.g. GPTQ's group size) or mixed-precision handling of outlier channels.
