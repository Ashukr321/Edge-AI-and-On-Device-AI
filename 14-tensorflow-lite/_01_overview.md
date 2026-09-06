# TensorFlow Lite / LiteRT — Overview

TensorFlow Lite (TFLite) is Google's lightweight inference runtime for deploying TensorFlow/Keras models on mobile, embedded, and IoT devices. In 2024 Google began rebranding the runtime as **LiteRT** ("Lite Runtime") to reflect that it is no longer TensorFlow-specific — it runs models exported from PyTorch (via ONNX) and JAX as well as TensorFlow. The `.tflite` file format, converter, and delegate architecture remain, but the project name, docs, and some tooling now use the LiteRT name; `tensorflow.lite` APIs continue to work for backward compatibility.

The runtime is designed around a small binary footprint, low-latency startup, and hardware acceleration through pluggable **delegates**, making it the standard choice for on-device inference on Android, iOS, Linux SBCs, and microcontrollers.
