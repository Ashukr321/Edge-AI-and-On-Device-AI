# Core ML — Tooling ecosystem

- **coremltools** — the Python conversion/optimization library (PyTorch/TensorFlow → Core ML, quantization, palettization, model spec editing).
- **Create ML** — no-code macOS training app for image/text/tabular/sound/motion classifiers, action classification, and recommendation models, exporting straight to `.mlpackage`.
- **Xcode Core ML model preview & Performance Report** — drag-and-drop model preview (test predictions on sample inputs directly in Xcode), plus on-device profiling that breaks down per-layer compute unit assignment and latency, run against a connected physical device.
- **Vision framework** — pre-built request types (`VNCoreMLRequest`, plus native Vision requests for face/text/barcode/pose detection) that wrap Core ML models for common CV pipelines.
- **Natural Language framework** — analogous wrapper for text embeddings, tokenization, and language identification, some of it backed by Core ML models Apple ships with the OS.
- **Model encryption via App Store Connect** — build-time encryption workflow for protecting model IP when distributing through the App Store.
- **`coremltools.optimize`** — the unified quantization/palettization/pruning API (superseding older, more scattered compression utilities).
