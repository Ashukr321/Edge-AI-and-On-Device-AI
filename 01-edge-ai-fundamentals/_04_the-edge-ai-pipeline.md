# Edge AI Fundamentals — The edge AI pipeline

A typical end-to-end workflow:

1. **Data collection** — gather representative data from the field
   (sensors, cameras, logs).
2. **Train in the cloud** — use full-precision models on GPU/TPU clusters
   with the full dataset (see `20-edge-ai-architecture` for the full loop).
3. **Optimize for the target** — quantization (FP32 → INT8/INT4), pruning,
   knowledge distillation, neural architecture search (NAS) for
   efficient architectures (MobileNet, EfficientNet, SqueezeNet family).
4. **Convert & compile** — export to an interchange format (ONNX) and
   compile/convert to a runtime-specific format (TFLite `.tflite`, Core ML
   `.mlmodel`/`.mlpackage`, TensorRT engine, OpenVINO IR).
5. **Deploy** — package the model with the app or firmware, or push via
   OTA update.
6. **Monitor & retrain** — collect performance/drift telemetry from the
   field and feed it back into the next training cycle.
