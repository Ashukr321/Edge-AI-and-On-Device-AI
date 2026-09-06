# Model Quantization — Key concepts

- **Precision formats.**
  - **FP32** — standard training precision, 4 bytes/value.
  - **FP16 / BF16** — 2 bytes/value; FP16 has a narrower exponent range (risk of overflow), BF16 keeps FP32's exponent range with fewer mantissa bits (common in training and increasingly in inference).
  - **INT8** — 1 byte/value; the most common inference quantization target, requires a scale (and sometimes zero-point) to map integers back to real values.
  - **INT4** — 0.5 bytes/value; common for LLM weight-only quantization (GPTQ, AWQ), where activations often stay higher precision.
  - **NF4 (NormalFloat4)** — a 4-bit format introduced by QLoRA, designed so quantization levels are spaced to match a normal distribution of weight values rather than being linearly spaced, giving better accuracy than plain INT4 for typical neural network weight distributions.
- **Affine quantization.** A real value `x` is mapped to an integer `q` via `q = round(x / scale) + zero_point`, and dequantized via `x ≈ (q - zero_point) * scale`. Symmetric quantization fixes `zero_point = 0` (simpler, common for weights); asymmetric quantization allows a nonzero zero-point (better for activations, which are often not centered at zero, e.g. post-ReLU).
- **Calibration.** Determining the right `scale`/`zero_point` requires observing a representative sample of activation values (a calibration dataset) to find the min/max or a percentile-based clipping range that minimizes quantization error/outlier clipping.
