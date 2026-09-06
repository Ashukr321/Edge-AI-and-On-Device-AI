# Local LLMs — CLI example

Using Ollama (wraps llama.cpp):

```bash
ollama pull llama3.1:8b
ollama run llama3.1:8b "Explain quantization in one paragraph."
```

Using llama.cpp directly with a downloaded GGUF file:

```bash
./llama-cli -m Meta-Llama-3.1-8B-Instruct-Q4_K_M.gguf \
  -p "Explain quantization in one paragraph." \
  -n 256 -c 4096 -ngl 33
```

`-ngl` (number of GPU layers) offloads that many transformer layers to GPU; `-c` sets context size.
