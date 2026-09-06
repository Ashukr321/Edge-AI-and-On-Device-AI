# TinyML — Trade-offs

| Factor | Full-size model | TinyML model |
|---|---|---|
| Accuracy | Higher, more headroom | Reduced by quantization + smaller architecture |
| Latency | Not power-constrained | Must fit real-time duty cycle, often <100 ms |
| Memory | GBs available | KBs to low MBs; hard ceiling |
| Power | Watts | Milliwatts, sometimes battery-year lifetimes |
| Development cost | Standard ML tooling | Cross-compilation, quantization-aware design, on-device profiling |

Shrinking a model for TinyML almost always costs some accuracy versus its float32 counterpart. The engineering discipline is in choosing the smallest model architecture (few layers, depthwise-separable convolutions, small input resolution) that still clears the task's accuracy bar, then quantizing carefully and validating on real hardware rather than only in simulation — MCU float emulation, memory layout, and cache behavior can all shift real-world latency versus desktop benchmarks.
