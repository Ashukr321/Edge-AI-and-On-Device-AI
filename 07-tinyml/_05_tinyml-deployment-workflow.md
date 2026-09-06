# TinyML — TinyML deployment workflow

1. **Train** a standard float32 model in TensorFlow/Keras (or PyTorch, then convert to ONNX/TF).
2. **Quantize to int8** using post-training quantization (or quantization-aware training for tighter accuracy retention) — see `08-model-quantization`. This shrinks the model ~4x and lets it run on FPU-less cores.
3. **Convert to TensorFlow Lite** (`.tflite` FlatBuffer format) via the TFLite Converter.
4. **Convert the FlatBuffer to a C byte array** (e.g. with `xxd -i model.tflite > model_data.cc`), since most MCU toolchains have no filesystem to load a model file from — the model is compiled directly into firmware flash.
5. **Write the inference application**: allocate a static tensor arena, instantiate the TFLM interpreter with the required op resolver, feed sensor data into the input tensor, invoke, and read the output tensor.
6. **Flash to device** via the vendor toolchain (Arduino IDE, PlatformIO, STM32CubeIDE) and validate against real sensor input, checking both accuracy and latency/power on-device.
