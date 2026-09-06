# Local LLMs — Hardware requirements (approximate, quantized GGUF)

Memory needed is roughly `parameters × bits_per_weight / 8`, plus overhead for KV cache and context.

| Model size | Q4_K_M (~4.5 bpw) | Q8_0 (~8.5 bpw) | Practical minimum |
|---|---|---|---|
| 3B | ~2 GB | ~3.5 GB | 8 GB RAM, runs fine on CPU |
| 7-8B | ~4.5-5 GB | ~8-9 GB | 8-16 GB RAM/VRAM |
| 13-14B | ~8-9 GB | ~15 GB | 16 GB RAM/VRAM |
| 34B | ~20 GB | ~36 GB | 24-32 GB VRAM or Apple Silicon unified memory |
| 70B | ~40 GB | ~75 GB | 48-64 GB (multi-GPU or high-RAM Apple Silicon) |
| Mixtral 8x7B (~47B total, ~13B active) | ~26 GB | ~48 GB | 32-48 GB |

Notes:
- Apple Silicon Macs (M-series unified memory) are popular for local LLMs because GPU and CPU share the same large memory pool — a 64GB MacBook can host a 70B Q4 model, something rare on a discrete-GPU laptop.
- A GPU with enough VRAM to hold the full model is fastest; partial GPU offload (some layers on GPU, rest on CPU) still helps but adds a PCIe transfer bottleneck.
- CPU-only inference is viable for 3B-8B models at usable speed (roughly single-digit to low-teens tokens/sec on modern desktop CPUs); larger models become painfully slow without a GPU.
