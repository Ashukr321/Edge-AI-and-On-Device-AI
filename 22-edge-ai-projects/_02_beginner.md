# Edge AI Projects — Beginner

1. **Real-time object detection on Android/iOS with TFLite / Core ML**
   Take a pretrained MobileNet-SSD or YOLO-nano model, convert it to
   TFLite (or Core ML on iOS), and run it on live camera frames using the
   phone's GPU/NNAPI delegate. Teaches the basic mobile inference loop:
   camera capture → preprocess → interpreter.run() → draw bounding boxes.
   *Stack: Android Studio + TensorFlow Lite (or Xcode + Core ML), a
   pretrained COCO detector.*

2. **Image classifier on a Raspberry Pi**
   Deploy a quantized MobileNet/EfficientNet-lite image classifier on a
   Raspberry Pi with a USB or CSI camera, using TFLite's CPU runtime (add
   a Coral USB Edge TPU accelerator as a stretch goal). Good first
   exposure to running inference on constrained ARM hardware outside a
   phone.
   *Stack: Raspberry Pi, TensorFlow Lite runtime, optional Coral Edge TPU.*

3. **Keyword spotting ("wake word") on a microcontroller**
   Train a tiny CNN/DS-CNN on a small keyword dataset (e.g. Google Speech
   Commands), quantize to INT8, and deploy to an Arduino Nano 33 BLE
   Sense or similar board using TensorFlow Lite for Microcontrollers.
   Introduces the full TinyML flow: KB-scale models, no OS, no dynamic
   memory allocation.
   *Stack: Arduino/ESP32, TensorFlow Lite Micro, Edge Impulse (optional,
   for the data pipeline).*

4. **On-device sentiment/text classifier in the browser**
   Run a small quantized text classification model fully client-side
   using ONNX Runtime Web or TensorFlow.js — no server call. Good
   introduction to WebAssembly/WebGL-backed in-browser inference.
   *Stack: ONNX Runtime Web or TensorFlow.js, a distilled BERT-family
   classifier.*
