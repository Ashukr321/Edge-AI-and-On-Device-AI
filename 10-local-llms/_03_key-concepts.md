# Local LLMs — Key concepts

- **Parameters**: model size, e.g. 7B = 7 billion weights. Roughly correlates with capability and required memory.
- **Quantization**: compressing weights from 16-bit floats down to 8, 5, 4, or even 2 bits per weight, trading a small quality loss for large memory/speed savings.
- **GGUF**: the file format used by llama.cpp and its ecosystem (successor to GGML) that bundles quantized weights, tokenizer, and metadata into a single portable file.
- **Context window**: how many tokens (prompt + generation) the model can attend to at once — commonly 8K-128K depending on model; larger contexts cost more KV-cache memory.
- **Tokens/sec (throughput)**: the practical speed metric. Prompt processing ("prefill") and generation ("decode") have different speeds; decode is usually the bottleneck for chat.
- **KV cache**: per-token memory used during generation to avoid recomputation; scales with context length and model size, and is often the hidden reason a model runs out of memory before the weights alone would.
- **MoE (Mixture of Experts)**: architectures like Mixtral activate only a subset of parameters per token, giving strong quality with sparser compute cost, though full weights still must reside in memory.
