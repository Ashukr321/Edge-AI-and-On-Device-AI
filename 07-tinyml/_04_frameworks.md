# TinyML — Frameworks

- **TensorFlow Lite for Microcontrollers (TFLM)** — the dominant runtime; C++ library with no dynamic memory allocation, no OS dependencies, and a small (tens of KB) core interpreter footprint. Runs `.tflite` (FlatBuffer) models converted from TensorFlow/Keras.
- **Edge Impulse** — an end-to-end MLOps platform for embedded devices: data collection from real sensors, signal processing (DSP) blocks, training, and one-click export to an optimized C++ library (often wrapping TFLM or its own EON compiler, which removes the interpreter entirely).
- **CMSIS-NN** — Arm's optimized neural-network kernel library for Cortex-M cores, providing hand-tuned SIMD (via CMSIS-DSP intrinsics) int8/int16 implementations of convolution, depthwise conv, fully connected, pooling, and activation ops. TFLM uses CMSIS-NN kernels internally on Arm targets.
- **uTensor** — an earlier, lightweight TinyML runtime (Mbed + TensorFlow) that emphasized generating minimal, offline-optimized C++ inference code rather than shipping a general-purpose interpreter. Largely superseded by TFLM but historically significant.
- **STM32Cube.AI (X-CUBE-AI)** — converts Keras/TFLite/ONNX models into optimized C code for STM32 parts.
- **microTVM** — Apache TVM's compiler-based path to microcontrollers, generating specialized C code rather than interpreting a graph.
