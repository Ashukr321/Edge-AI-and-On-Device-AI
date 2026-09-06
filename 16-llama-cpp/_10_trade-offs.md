# llama.cpp — Trade-offs

- Maximum portability and minimal dependencies versus less throughput-per-GPU than datacenter-oriented engines like vLLM or TensorRT-LLM for high-concurrency serving.
- K-quants give strong quality-per-byte but quantization is still lossy; for tasks sensitive to precision (complex reasoning, code generation with exact syntax needs), Q5/Q6/Q8 or full-precision may be worth the extra memory.
- Building from source requires picking the right backend flags for your hardware, which is more setup friction than a wrapper tool like Ollama, in exchange for finer control.
