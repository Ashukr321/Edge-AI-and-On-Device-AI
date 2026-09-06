# Edge AI Fundamentals — Core techniques

- **Quantization**: representing weights/activations in INT8, INT4, or
  mixed precision instead of FP32, cutting memory and often giving large
  speedups on hardware with integer math units. Post-training quantization
  (PTQ) is fast but can lose accuracy; quantization-aware training (QAT)
  recovers most of it.
- **Pruning**: removing redundant weights or entire channels/filters
  (structured pruning is more hardware-friendly than unstructured sparsity).
- **Knowledge distillation**: training a small "student" model to mimic a
  large "teacher" model's outputs.
- **Efficient architectures**: depthwise-separable convolutions
  (MobileNet), neural architecture search (EfficientNet), and
  transformer variants designed for mobile (MobileViT, MobileBERT).
- **Operator fusion & graph optimization**: compilers fuse conv+batchnorm+
  relu chains, eliminate dead nodes, and pick kernels tuned for the target
  chip.
