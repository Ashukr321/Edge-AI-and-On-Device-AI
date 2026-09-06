# Local LLMs — Context window and speed considerations

- Longer contexts increase KV-cache memory linearly and slow prefill; a 32K-context request costs meaningfully more RAM than an 8K one for the same model.
- Prefill (processing the prompt) is usually GPU-bound and fast; decode (generating tokens one at a time) is memory-bandwidth bound, which is why VRAM bandwidth (not just capacity) matters for speed.
- Typical decode speeds people report: a 7-8B Q4 model can hit 30-80+ tokens/sec on a modern consumer GPU, 5-15 tokens/sec on CPU-only; a 70B Q4 model on a capable multi-GPU or Apple Silicon setup often lands in the 5-15 tokens/sec range.
- These numbers vary widely by hardware generation and software version — always benchmark on your own machine rather than trust a number from elsewhere.
