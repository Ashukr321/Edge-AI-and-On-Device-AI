# llama.cpp — Key concepts

- **GGML**: the underlying tensor library (also by Gerganov) providing the compute backend, quantization kernels, and low-level graph execution that llama.cpp is built on.
- **GGUF**: the model file format (successor to the older GGML format) — a single binary file containing quantized weights, tokenizer, and architecture metadata, designed for fast mmap-based loading.
- **No Python/CUDA requirement**: the core engine is pure C/C++ and can be compiled to run CPU-only with zero GPU dependencies; GPU backends are optional compile-time additions, not requirements.
- **mmap loading**: model files are memory-mapped rather than fully read into a separate buffer, letting the OS page in weights on demand and enabling multiple processes to share the same cached weights.
