# Local Vision Models — Trade-offs

- Nano/lite models sacrifice accuracy (especially on small objects or rare classes) for the speed needed at real-time frame rates.
- INT8 quantization is nearly free for most CNN vision backbones but can hurt fine detection/segmentation boundaries more than it hurts classification.
- Small VLMs are convenient but noticeably weaker than large multimodal models at complex reasoning about an image (counting, spatial relationships, dense OCR-in-image reading).
- Task-specific frameworks (MediaPipe) trade flexibility for a much faster path to production compared to hand-rolling a pipeline from raw ONNX/TFLite models.
