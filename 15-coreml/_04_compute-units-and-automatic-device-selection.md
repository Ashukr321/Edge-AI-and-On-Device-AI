# Core ML — Compute units and automatic device selection

Core ML does not require the developer to manually partition the graph. Given a compute unit hint (default `.all`), it:
- Analyzes the graph at load/compile time (`.mlmodelc` compilation).
- Assigns each op/layer to CPU, GPU, or ANE based on operator support, data types, and heuristics about which is fastest for that shape.
- Falls back to CPU (or GPU) for ops the ANE doesn't support, similar in spirit to ONNX Runtime's/TFLite's delegate fallback behavior, but handled entirely inside the OS/runtime rather than via an app-selectable plugin.
- Uses `MLModelConfiguration.computeUnits` to constrain this (e.g. force `.cpuOnly` for deterministic debugging, or `.cpuAndGPU` to avoid ANE precision quirks for some numerically sensitive models).

The ANE favors float16 and specific op patterns (standard convolutions, attention blocks in recent chips); models with unusual custom ops, dynamic shapes, or unsupported control flow tend to fall back to GPU/CPU, which is the most common cause of unexpectedly slow on-device performance.
