# TensorFlow Lite / LiteRT — Trade-offs

**Strengths**
- Small runtime footprint and fast cold-start, ideal for mobile app size budgets.
- Mature, wide delegate ecosystem tuned specifically for Android/iOS hardware.
- Single codebase scales from full Android/iOS apps down to microcontrollers (TFLM), unusual breadth.
- Strong first-party integration with Android tooling (Android Studio ML Model Binding, ML Kit).

**Weaknesses**
- No native PyTorch converter — cross-framework conversion (via ONNX or `ai-edge-torch`) can hit unsupported-op friction, same class of issue as any cross-format export.
- Op coverage for exotic/custom layers lags behind full TensorFlow; "Select TF ops" fallback bloats binary size.
- Full-integer quantization requires a representative calibration dataset and can meaningfully shift accuracy for sensitive models if not validated carefully.
- The TFLite→LiteRT rebrand has created some transitional confusion in docs/tutorials, with both names appearing depending on the resource's age.
