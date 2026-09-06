# Core ML — Trade-offs

**Strengths**
- Best-in-class integration with Apple hardware — the only path that reliably reaches the Apple Neural Engine.
- Automatic compute-unit scheduling removes a whole class of manual backend-selection work developers face with other runtimes.
- Strong tooling inside Xcode for profiling and debugging directly against real devices.
- First-class model protection (encryption) for commercial App Store apps.

**Weaknesses**
- Apple-only — no path to Android, Windows, Linux, or the web; multi-platform apps need a second runtime (e.g. ONNX Runtime, LiteRT) alongside Core ML.
- Conversion coverage lags bleeding-edge PyTorch ops; custom/exotic layers can require writing a custom coremltools op translation.
- ANE behavior is partly a black box — Apple doesn't expose fine-grained control over what runs on the ANE beyond compute-unit hints, so unexpected CPU/GPU fallback requires the Performance Report to diagnose rather than being visible from code.
- Because OS and hardware evolve together, older `.mlmodel`/older coremltools-converted models can behave differently (performance or precision) across iOS versions.
