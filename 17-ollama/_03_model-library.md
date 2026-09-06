# Ollama — Model library

Ollama's registry covers most major open-weight families (Llama 3.x, Mistral/Mixtral, Gemma 2/3, Qwen2.5, Phi-3/4, DeepSeek distills, and many fine-tunes) each pre-converted to GGUF with multiple quantization tags, e.g. `llama3.1:8b`, `llama3.1:8b-instruct-q4_K_M`, `llama3.1:70b`. Pulling a tag with no size (`ollama pull llama3.1`) picks a sensible default variant.
