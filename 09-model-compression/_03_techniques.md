# Model Compression — Techniques

### Pruning

- **Magnitude pruning**: remove the weights with the smallest absolute value, on the premise that small weights contribute least to the output. Usually done iteratively — prune a percentage, fine-tune to recover accuracy, repeat — rather than in one shot.
- **Structured pruning**: remove entire filters/channels/heads based on an importance criterion (e.g. L1-norm of a filter, or a learned gate). Produces a genuinely smaller dense model with no need for sparse-matrix support.
- **The Lottery Ticket Hypothesis** (Frankle & Carbin, 2019): a randomly-initialized dense network contains a much smaller subnetwork ("winning ticket") that, when trained in isolation from the same initialization, matches the full network's accuracy. This reframed pruning from "shrink after training" to a claim about which subnetworks were trainable from the start, and motivated pruning-at-initialization research.
- Pruning is typically followed by fine-tuning (or full retraining) to recover accuracy lost from removed capacity.

### Knowledge distillation

A smaller "student" model is trained to reproduce the behavior of a larger "teacher" model, using the teacher's output probabilities (soft labels, often temperature-scaled to soften the distribution) as an additional training signal alongside or instead of the ground-truth hard labels. The intuition is that soft labels carry more information than one-hot labels — e.g. how confidently the teacher confuses a "3" for an "8" — which helps the smaller model generalize better than training on ground truth alone.

- **DistilBERT**: a 6-layer distilled version of BERT-base (12 layers), retaining roughly 97% of BERT's language-understanding benchmark performance while being about 40% smaller and ~60% faster at inference, using a distillation loss combined with the original masked-language-modeling loss.
- **MobileBERT**: a distillation-and-architecture-redesign approach that produces a BERT-sized-depth but much narrower ("bottleneck") model specifically tuned for mobile latency, distilled from an inverted-bottleneck teacher.
- Distillation can also transfer intermediate representations (hidden states, attention maps) rather than only final output logits, which often improves student quality further.

### Low-rank factorization

Weight matrices (especially large fully-connected or embedding layers) are approximated as a product of two smaller matrices, `W ≈ A·B` where `A` and `B` have a much smaller inner rank than `W`'s original dimensions. This directly reduces parameter count and FLOPs for the affected layer. It's the same underlying idea used in LoRA for efficient fine-tuning, though there it's applied as an additive adapter rather than a wholesale layer replacement.

### Neural architecture search (NAS) for efficient models

Rather than compressing an existing large model, NAS searches (manually or automatically) for architectures that are efficient by design:

- **SqueezeNet**: an early (2016) example, using "fire modules" (a squeeze layer of 1x1 convolutions feeding an expand layer) to cut parameter count roughly 50x versus AlexNet at similar accuracy.
- **MobileNet (V1/V2/V3)**: introduced depthwise-separable convolutions (a depthwise spatial convolution followed by a pointwise 1x1 convolution), which approximate a standard convolution at a fraction of the multiply-accumulate cost. MobileNetV3 was tuned partly via NAS combined with the NetAdapt algorithm for per-layer latency targets, plus the "hard-swish" activation designed for quantization friendliness.
- **EfficientNet**: introduced compound scaling — jointly scaling network depth, width, and input resolution by a single coefficient rather than tuning them independently — derived from a NAS-found baseline architecture (EfficientNet-B0).
- These architectures are frequently the starting point for edge deployment, then further compressed via pruning/quantization on top.

### Weight sharing / clustering

Weights are clustered (e.g. via k-means) into a small number of groups, and each weight is replaced by an index into a shared codebook of centroid values. This doesn't reduce the number of multiply-accumulate operations at inference but reduces storage, since the model can be stored as small integer indices plus a small codebook instead of full-precision weights — most effective as a compression-for-storage/transfer technique, and combines well with subsequent quantization of the codebook itself. Popularized as part of the "Deep Compression" pipeline (Han et al., 2016), which chained pruning, weight clustering, and Huffman coding.
