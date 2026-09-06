# iOS Edge AI — Model formats / deployment workflow

1. Train in PyTorch or TensorFlow, or train directly with **Create ML** for supported task templates.
2. Convert with `coremltools` to `.mlpackage` (ML Program backend).
3. Quantize/palettize with `coremltools.optimize` to hit size/latency targets.
4. Optionally encrypt the compiled model archive for IP protection using Xcode's model-encryption option (generates a key managed via CloudKit/your backend, decrypted on-device at load).
5. Add the `.mlpackage` to the Xcode project; Xcode compiles it into `.mlmodelc` at build time (or the OS compiles it on first install for on-demand resources).
6. Load via the generated Swift model class or dynamically via `MLModel(contentsOf:configuration:)`.
7. Profile with Xcode Instruments' Core ML template before shipping.
