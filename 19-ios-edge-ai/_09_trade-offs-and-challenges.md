# iOS Edge AI — Trade-offs & challenges

- **ANE op coverage gaps**: architecture choices that aren't ANE-friendly silently fall back to GPU/CPU, and this is only visible through profiling, not the API surface.
- **Conversion fidelity**: PyTorch/TensorFlow → Core ML conversion can introduce numerical drift or require custom op implementations for exotic layers.
- **Device fragmentation, narrower than Android but real**: ANE generation varies across A-series/M-series chips, affecting both available capability and achievable performance.
- **Foundation Models framework availability**: gated to Apple Intelligence-capable devices/OS versions, so apps need a fallback path (or feature gating) for unsupported hardware.
- **Model IP protection**: encryption adds a key-management dependency (typically via a backend or CloudKit) and a small load-time cost.
