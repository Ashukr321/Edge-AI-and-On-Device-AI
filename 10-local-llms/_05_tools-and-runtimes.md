# Local LLMs — Tools & runtimes

- **llama.cpp** — the foundational C/C++ inference engine for GGUF models; CPU-first with optional GPU backends (CUDA, Metal, Vulkan, SYCL). See `16-llama-cpp/README.md`.
- **Ollama** — a friendly CLI/daemon wrapper around llama.cpp with a model registry and simple `pull`/`run` workflow. See `17-ollama/README.md`.
- **LM Studio** — a desktop GUI app (macOS/Windows/Linux) for browsing, downloading, and chatting with local GGUF models, with an OpenAI-compatible local server mode.
- **vLLM** — a high-throughput serving engine designed for GPU datacenter/workstation use with PagedAttention; overkill for a single chat session but useful for local multi-user serving with a decent GPU.
- **MLC-LLM** — compiles models via TVM for deployment across CUDA, Metal, WebGPU, and mobile (Android/iOS) backends; used when targeting phones or browsers directly.
- **text-generation-webui** — a Gradio-based UI supporting multiple backends (llama.cpp, ExLlama, Transformers) for experimentation.
