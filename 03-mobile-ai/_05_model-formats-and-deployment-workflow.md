# Mobile AI — Model formats & deployment workflow

The typical pipeline, regardless of platform:

1. **Train** in PyTorch or TensorFlow/Keras on server-class hardware.
2. **Export/convert** to a mobile-friendly format:
   - PyTorch → ExecuTorch `.pte`, or → ONNX → ONNX Runtime Mobile, or → Core ML via `coremltools`.
   - TensorFlow/Keras → `.tflite` via the LiteRT converter, or → Core ML via `coremltools`.
3. **Quantize** the converted model (post-training quantization is the common default; quantization-aware training when accuracy loss is unacceptable).
4. **Validate** accuracy and latency on representative devices — not just the converter's dummy-input pass, since operator support gaps only show up at real inference time.
5. **Bundle or defer**: embed the model in the app package for features that must work offline/on first launch, or fetch it on demand (Play Feature Delivery, Apple's on-demand resources, or a plain CDN download) for larger or frequently updated models.
6. **Ship, monitor, iterate**: track on-device latency/crash telemetry, and plan for model updates independent of app releases where possible.
