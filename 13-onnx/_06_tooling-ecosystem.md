# ONNX & ONNX Runtime — Tooling ecosystem

- **Netron** — the standard tool for visualizing `.onnx` (and `.tflite`, `.mlmodel`, etc.) graphs in a browser or desktop app; essential for debugging exported graphs, checking op names, shapes, and where a conversion diverged.
- **ONNX Runtime Extensions** — a companion library providing custom ops not in core ONNX (text tokenization, image decoding, string ops), useful for end-to-end pipelines (e.g. embedding a BERT tokenizer directly in the graph).
- **onnxruntime.quantization** — static/dynamic PTQ tooling, calibration data readers, QDQ (Quantize-DeQuantize) format support.
- **onnxruntime.transformers.optimizer** — transformer-specific graph fusions (attention fusion, LayerNorm fusion) for BERT/GPT-style models.
- **onnxsim (onnx-simplifier)** — simplifies/cleans exported graphs, removing redundant nodes often left by exporters.
- **onnx.checker / onnx.shape_inference** — validate graph well-formedness and infer intermediate shapes.
- **Olive** (Microsoft) — an optimization pipeline that automates export, quantization, and EP-specific tuning for ONNX Runtime deployment targets.
- **ONNX Runtime Mobile** — a reduced-size ORT build (custom ops trimmed via a build-time operator reduction) plus the `.ort` format, for Android/iOS app binary size constraints.
- **onnxruntime-web / onnxruntime-node** — JS bindings for browser and Node.js deployment.
