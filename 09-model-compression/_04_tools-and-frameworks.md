# Model Compression — Tools & frameworks

| Tool | Ecosystem | What it provides |
|---|---|---|
| TensorFlow Model Optimization Toolkit (TF-MOT) | TensorFlow/Keras | Magnitude pruning (`tfmot.sparsity.keras`), weight clustering, and QAT APIs, all designed to compose together |
| `torch.nn.utils.prune` | PyTorch | Built-in unstructured/structured pruning utilities (`l1_unstructured`, `ln_structured`, custom pruning methods), applies pruning masks in-place on existing modules |
| Distiller | PyTorch (Intel, community-maintained) | A research/production framework for pruning, quantization, and knowledge-distillation experiments with configurable YAML-driven pipelines |
| Hugging Face Optimum | PyTorch/ONNX | Integrates pruning, quantization, and distillation-friendly export paths (ONNX Runtime, OpenVINO, TensorRT backends) for Transformer models |
| Neural Network Intelligence (NNI, Microsoft) | Cross-framework | AutoML toolkit including pruning and NAS algorithms |
