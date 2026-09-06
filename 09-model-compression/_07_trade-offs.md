# Model Compression — Trade-offs

| Technique | Size reduction | Speed impact | Accuracy risk | Engineering cost |
|---|---|---|---|---|
| Unstructured pruning | High (with sparse storage) | Needs sparse kernel support to realize speedup | Low–moderate with iterative fine-tuning | Moderate |
| Structured pruning | Moderate–high | Direct speedup on any hardware | Moderate (removes whole capacity units) | Moderate–high (need importance criteria, retraining) |
| Knowledge distillation | Depends on student architecture chosen | Direct (smaller model, fewer FLOPs) | Low if teacher is much stronger and training is done well | High (needs teacher, longer training) |
| Low-rank factorization | Moderate | Direct for factorized layers | Moderate, depends on rank chosen | Low–moderate |
| Weight clustering | Storage only, no FLOP reduction | None at inference (indices still expand to full compute) unless paired with quantization | Low | Low |
| Efficient NAS architecture | Designed-in from the start | Designed-in from the start | Baseline is the trade-off, not an add-on cost | High (search cost, though largely a one-time community cost via published architectures) |

The overarching trade-off across all of these techniques is accuracy versus size/speed, but the *slope* of that trade-off differs: distillation and NAS-designed efficient architectures tend to give the best accuracy-per-parameter, while post-hoc pruning of an existing model is cheaper to apply but usually yields a worse accuracy/compression frontier at very high compression ratios. Combining techniques (efficient architecture + light pruning + quantization) generally beats pushing any single technique to its limit.
