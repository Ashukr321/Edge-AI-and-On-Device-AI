# Ollama — Overview

Ollama packages llama.cpp's inference engine behind a simple CLI and background daemon, adding a model registry, one-line pulls, and automatic hardware-appropriate configuration (GPU detection, sensible defaults). Where llama.cpp asks you to find a GGUF file and pick your own flags, Ollama turns that into `ollama pull llama3.1` and `ollama run llama3.1`. It runs on macOS, Linux, and Windows, ships an OpenAI-compatible API, and has become the most common on-ramp for developers who want a local model without learning llama.cpp's build system directly.
