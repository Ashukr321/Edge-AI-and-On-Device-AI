# llama.cpp — Performance tuning flags

| Flag | Effect |
|---|---|
| `-t <n>` | CPU thread count for computation; usually best set to physical core count, not hyperthreads |
| `-tb <n>` | Threads used specifically for batch/prompt processing, can differ from generation threads |
| `-ngl <n>` | GPU layers to offload; set to the model's total layer count to run fully on GPU, lower for partial offload when VRAM is limited |
| `-c <n>` | Context size; larger values increase KV-cache memory roughly linearly |
| `-b <n>` | Batch size for prompt processing; larger batches speed up prefill at the cost of memory |
| `--mlock` | Locks model pages in RAM, preventing swapping (needs sufficient free RAM) |
| `--no-mmap` | Disables mmap loading, forcing full read into RAM; occasionally needed on filesystems where mmap is slow |
| `-fa` | Enables flash-attention kernel where supported, reducing memory and improving speed for long contexts |

Finding the right `-ngl` for a GPU with limited VRAM is usually the single biggest speed lever: as many layers as fit in VRAM without spilling, leaving the rest on CPU.
