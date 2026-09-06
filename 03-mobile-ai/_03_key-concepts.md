# Mobile AI — Key concepts

- **On-device inference vs. cloud inference vs. hybrid**: privacy, latency, and offline-availability push work to the device; model size and accuracy sometimes push it to the cloud. Many production features (e.g., voice assistants) use hybrid pipelines — a small on-device model for wake-word/intent triage, a larger cloud model for full understanding.
- **Quantization**: reducing weight/activation precision (FP32 → FP16/BF16 → INT8 → INT4) to shrink model size and speed up inference, usually with a small accuracy cost.
- **Delegates / backends**: an abstraction that lets a single model file run on CPU, GPU, DSP, or NPU depending on what the device exposes, without rewriting the model.
- **Operator coverage**: not every op a model uses is guaranteed to be supported by every accelerator delegate; unsupported ops fall back to CPU, which can dominate latency.
- **Model compression**: pruning, distillation, and weight clustering, layered on top of quantization to hit tighter size/latency budgets.
- **Dynamic/deferred model delivery**: shipping the app without the model and fetching it after install, or fetching newer model versions post-launch, to keep the initial app package small.
