# TensorFlow Lite / LiteRT — LiteRT Next and project direction

Google's stated direction is to unify inference across TensorFlow, PyTorch, and JAX-origin models under the LiteRT name, with two notable shifts:
- **LiteRT Next**: a newer C++/Kotlin API that simplifies accelerator/delegate selection (a single "compiled model" concept instead of manually wiring delegates) and adds async execution and hardware buffer interop for zero-copy pipelines (e.g. camera frame → GPU tensor without a CPU round-trip).
- **On-device generative AI**: increasing investment in running small LLMs on-device (e.g. via MediaPipe LLM Inference API / LiteRT), reflecting that the runtime's use cases have expanded well beyond classic CNN/vision workloads.
- The `tensorflow.lite` Python/Java namespaces continue to function, so existing TFLite code is not broken by the rebrand — LiteRT is presented as the same runtime under new branding and a modernized API layer, not a fork.
