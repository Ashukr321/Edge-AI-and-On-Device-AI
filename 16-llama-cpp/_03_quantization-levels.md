# llama.cpp — Quantization levels

llama.cpp popularized a family of quantization schemes, most now "K-quants" (structure-aware quantization that varies bits-per-weight across tensor blocks for better quality retention):

| Quant | Approx bits/weight | Notes |
|---|---|---|
| Q2_K | ~2.6 | Smallest, noticeable quality loss, mainly for very large models where any quant beats not fitting at all |
| Q3_K_S/M/L | ~3.4-3.9 | Small footprint, larger quality gap versus Q4+ |
| Q4_0 / Q4_K_M | ~4.5-5.0 | Widely considered the best size/quality balance; Q4_K_M is the most commonly recommended default |
| Q5_K_M | ~5.5 | Noticeably better quality than Q4 for modest extra size |
| Q6_K | ~6.6 | Close to fp16 quality, larger file |
| Q8_0 | ~8.5 | Near-lossless versus the original weights, ~2x the size of Q4 |
| F16 / BF16 | 16 | Unquantized, reference quality, largest |

K-quants (the `_K_` variants) generally outperform the older uniform quants (`Q4_0`, `Q4_1`) at the same bit width because they allocate precision non-uniformly based on which weights matter more.
