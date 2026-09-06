# Ollama — Key concepts

- **Model library**: a hosted registry (ollama.com/library) of pre-quantized, ready-to-pull models — Llama, Mistral, Gemma, Qwen, Phi, and community fine-tunes — each with several quantization/size tags.
- **Modelfile**: a Dockerfile-like text format for defining or customizing a model — base model, system prompt, parameters, and templates — built into a new named model with `ollama create`.
- **Daemon (`ollama serve`)**: a background service that loads/unloads models on demand, keeping recently used models warm in memory and evicting them after an idle timeout.
- **Layered storage**: models are stored content-addressed (similar to container image layers), so multiple Modelfiles built from the same base model share the underlying weight blob on disk.
