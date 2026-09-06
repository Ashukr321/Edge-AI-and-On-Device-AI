# llama.cpp — CLI usage example

```bash
# Basic single-prompt generation
./build/bin/llama-cli -m model-Q4_K_M.gguf -p "Explain KV cache in two sentences." -n 200

# Interactive chat mode
./build/bin/llama-cli -m model-Q4_K_M.gguf -cnv

# Key flags:
#   -t 8          number of CPU threads
#   -c 8192       context size (tokens)
#   -ngl 33       number of transformer layers offloaded to GPU (0 = CPU only)
#   -n 256        max tokens to generate
#   --temp 0.7    sampling temperature
```
