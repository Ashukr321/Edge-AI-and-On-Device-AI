# Edge AI Projects — Intermediate

5. **Quantize and deploy a vision model to a microcontroller with TinyML**
   Take a slightly larger vision model (e.g. person detection), apply
   post-training INT8 quantization, and deploy it to an MCU-class board
   with a low-res camera module. Focus on the accuracy-vs-footprint
   trade-off by comparing FP32 vs. INT8 vs. pruned variants.
   *Stack: Edge Impulse or TensorFlow Lite Micro, an Arduino/STM32 board
   with a camera module.*

6. **Offline voice assistant with whisper.cpp**
   Run OpenAI's Whisper speech-to-text model fully offline using the
   whisper.cpp C++ port (quantized ggml weights) on a laptop or Raspberry
   Pi 4/5, wired up to a simple command-parsing layer. Demonstrates
   running a genuinely useful model with zero cloud dependency.
   *Stack: whisper.cpp, a microphone, a small rule-based or intent-
   classification layer on top of the transcript.*

7. **Edge video analytics pipeline on NVIDIA Jetson**
   Build a multi-stage pipeline (decode → object detection → tracking →
   event logging) on a Jetson Nano/Orin using TensorRT-optimized models,
   simulating a real industrial/retail analytics deployment.
   *Stack: NVIDIA Jetson, TensorRT, DeepStream SDK (optional) or a custom
   OpenCV + TensorRT pipeline.*

8. **Federated learning simulation across simulated edge clients**
   Implement FedAvg from scratch (or using Flower/TensorFlow Federated)
   to train an image classifier across several simulated "client" data
   partitions without centralizing the data, comparing convergence to
   centralized training.
   *Stack: Flower or TensorFlow Federated, PyTorch/TensorFlow, a
   partitioned dataset (e.g. non-IID splits of CIFAR-10/FEMNIST).*

9. **Model cascading: on-device filter + cloud fallback**
   Build a two-stage pipeline where a small on-device model handles the
   easy majority of inputs and forwards only low-confidence cases to a
   cloud API, then measure the bandwidth/cost savings versus always
   calling the cloud.
   *Stack: TFLite/Core ML on-device model, a cloud inference endpoint
   (self-hosted or a hosted API), a confidence-threshold router.*

10. **A/B testing and staged rollout harness for an on-device model**
    Simulate a fleet of "devices" (processes/containers) each pinned to a
    model version via a feature flag, push a staged rollout of a new
    model version, and build a small dashboard tracking per-cohort
    latency/error metrics with an automatic rollback rule.
    *Stack: any inference runtime, a feature-flag mechanism (config file
    or a tool like Unleash), a simple metrics dashboard.*
