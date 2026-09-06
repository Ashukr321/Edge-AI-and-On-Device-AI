# Local Vision Models — Key concepts

- **Backbone**: the feature-extracting network (MobileNet, EfficientNet, ResNet variants) shared across classification/detection/segmentation heads.
- **Depthwise separable convolutions**: the core trick behind MobileNet's efficiency — factoring a standard convolution into a per-channel spatial pass and a 1x1 channel-mixing pass, cutting compute substantially.
- **Anchor-free vs. anchor-based detection**: modern detectors (YOLOv8+, EfficientDet) increasingly use anchor-free heads for simpler post-processing.
- **Quantization (INT8)**: converting float weights/activations to 8-bit integers for 2-4x speedup on CPUs/NPUs with typically small accuracy loss; post-training quantization and quantization-aware training are the two main approaches.
- **NPU/delegate**: hardware accelerators exposed through a runtime "delegate" (e.g. TFLite's NNAPI/Core ML/XNNPACK delegates) that route ops to specialized silicon instead of the CPU.
- **Vision-language model (VLM)**: a model pairing a vision encoder with a language model to answer questions about or describe images; compact edge variants trade some accuracy for a footprint small enough to run locally.
