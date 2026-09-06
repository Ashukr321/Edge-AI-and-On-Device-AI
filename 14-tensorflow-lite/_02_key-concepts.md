# TensorFlow Lite / LiteRT — Key concepts

| Term | Meaning |
|---|---|
| **`.tflite`** | A FlatBuffer-serialized model: a flat, zero-copy binary format optimized for fast mmap-based loading, unlike protobuf which requires deserialization. |
| **Interpreter** | The runtime object that loads a `.tflite` model, allocates tensors, and runs inference. Present in Python, Java/Kotlin, Swift/Objective-C, and C++ APIs. |
| **Delegate** | A plugin that offloads part or all of the graph to specialized hardware (GPU, DSP, NPU). Analogous to ONNX Runtime's Execution Providers. |
| **Converter** | `tf.lite.TFLiteConverter` — transforms a SavedModel, Keras model, or concrete function into a `.tflite` FlatBuffer, optionally applying quantization during conversion. |
| **Ops (builtin vs. Select TF ops)** | TFLite ships a curated set of "builtin" mobile-friendly ops; models using ops outside that set can pull in "Select TensorFlow ops" (larger binary) as a fallback. |
| **Signature** | Named input/output entry points on a converted model (replacing the old single-input/output assumption), useful for multi-function models (e.g. encoder + decoder). |
| **LiteRT Next** | The newer API surface (still evolving) unifying delegate/accelerator selection and adding first-class support for on-device LLMs and multi-backend compiled models. |
