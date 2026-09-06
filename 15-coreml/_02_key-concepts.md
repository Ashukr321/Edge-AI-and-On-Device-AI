# Core ML — Key concepts

| Term | Meaning |
|---|---|
| **`.mlmodel` / `.mlpackage`** | Serialized Core ML model formats. `.mlpackage` (introduced with Core ML 5) supports larger models, multiple precisions, and richer metadata; Xcode compiles either into an optimized `.mlmodelc` at build time. |
| **MLModel** | The runtime class representing a loaded model; generated Swift model classes wrap it with typed input/output accessors. |
| **Compute Units** | `.cpuOnly`, `.cpuAndGPU`, `.cpuAndNeuralEngine`, `.all` — a hint controlling which hardware Core ML is allowed to schedule the model onto. |
| **ANE (Apple Neural Engine)** | Apple's dedicated NPU, present since the A11/A-series and M-series chips; Core ML automatically compiles compatible ops/layers onto it when `.all` (default) is used. |
| **Model encryption** | Core ML models can be encrypted at build/export time so weights aren't extractable from the shipped `.ipa`, decrypted only in a secure enclave-backed path at load time on-device. |
| **Palettization / quantization** | Weight-compression techniques in `coremltools.optimize` — palettization clusters weights into a lookup table (like a color palette) to shrink model size with less accuracy loss than blunt quantization in some cases; linear/blockwise quantization reduces precision to int8/int4. |
| **Create ML** | A no-code macOS app (and Swift framework) for training common task models (image classifiers, object detectors, text classifiers, tabular models, sound classifiers) directly to Core ML format. |
