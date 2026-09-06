# iOS Edge AI — Key concepts

- **Unified model package**: Core ML models are distributed as `.mlmodel` (legacy) or the newer `.mlpackage` directory format, compiled at build/install time (or first launch) into a device-specific `.mlmodelc` for execution.
- **Compute unit selection**: Core ML automatically partitions a model graph across CPU, GPU, and ANE, or lets the app constrain which units to use (`.cpuOnly`, `.cpuAndGPU`, `.all`, `.cpuAndNeuralEngine`).
- **Apple Neural Engine (ANE)**: Apple's dedicated low-power matrix-multiply accelerator, present in A-series and M-series chips; best throughput-per-watt for supported ops (mainly convolution- and transformer-friendly operations), but with a narrower op set than CPU/GPU.
- **Model encryption**: Core ML supports encrypting `.mlmodelc` model archives so weights aren't readable from the app bundle on disk, decrypted only at load time using a key fetched at runtime.
- **On-device foundation model**: iOS 18+ (Apple Intelligence-capable devices) exposes a several-billion-parameter on-device LLM through the Foundation Models framework, usable directly by third-party apps via Swift APIs (guided generation, tool calling) without network calls.
