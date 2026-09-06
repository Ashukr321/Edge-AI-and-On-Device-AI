# Local LLMs — Overview

A "local LLM" setup loads model weights into memory on hardware you control and runs inference without a network round-trip to a provider. The practice took off in 2023-2024 once open-weight models (Llama, Mistral) reached usable quality and quantization techniques shrank memory footprints enough to fit on consumer GPUs and even CPUs. By 2025-2026 it's routine to run a competent 7-14B assistant model on an 8-16GB laptop, and 70B-class models on prosumer workstations with 48-64GB unified memory or multi-GPU rigs.
