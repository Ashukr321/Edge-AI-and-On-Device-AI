# TensorFlow Lite / LiteRT — Core workflow: convert → optimize → deploy

1. **Train** in TensorFlow/Keras, or import from another framework.
2. **Convert to `.tflite`**:
   - From Keras: `tf.lite.TFLiteConverter.from_keras_model(model)`
   - From a SavedModel: `TFLiteConverter.from_saved_model(path)`
   - From a concrete function: `TFLiteConverter.from_concrete_functions([...])`
   - **From PyTorch**: no direct converter — the common path is PyTorch → ONNX → `onnx-tf` / `ai-edge-torch` → TFLite. Google's `ai-edge-torch` library is the more actively maintained modern path for PyTorch → LiteRT.
3. **Apply post-training quantization** (optional, during conversion) — dynamic range, full-integer (INT8) with a representative dataset, or float16.
4. **Validate** — run the same inputs through the original model and the `.tflite` model, and compare output tensors for acceptable drift, especially after INT8 quantization.
5. **Select delegate(s)** at runtime based on target device, with CPU (XNNPACK) as the always-available fallback.
6. **Deploy** — bundle the `.tflite` file in the app (Android assets, iOS bundle) and invoke it through the Interpreter API, or via Google's **MediaPipe Tasks** / **ML Kit** higher-level APIs for common tasks (classification, detection, segmentation, LLM inference).
7. **(Microcontrollers)** convert the model further into a C byte array and link against **TensorFlow Lite for Microcontrollers (TFLM)** — a distinct, dependency-free C++ runtime subset designed for devices with only kilobytes of RAM and no OS (e.g. Cortex-M, ESP32).
