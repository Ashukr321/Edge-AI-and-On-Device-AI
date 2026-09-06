# Ollama — Trade-offs

- Ollama trades llama.cpp's fine-grained flag control for convenience — you generally can't tune every llama.cpp performance flag directly, though `num_ctx`, `num_gpu` (layers), and a few others are exposed via Modelfile parameters or environment variables (`OLLAMA_NUM_PARALLEL`, `OLLAMA_MAX_LOADED_MODELS`, `OLLAMA_KEEP_ALIVE`).
- The idle-unload behavior (default keep-alive ~5 minutes) trades memory efficiency for a cold-start delay on the next request after a model is evicted.
- Because it re-packages llama.cpp releases on its own cadence, day-one support for a brand-new architecture sometimes lags directly building latest llama.cpp from source.
- Running multiple concurrent requests against one model works but is not tuned for high-throughput multi-user serving the way vLLM or TensorRT-LLM are — Ollama is optimized for single-user/local-app convenience, not datacenter concurrency.
