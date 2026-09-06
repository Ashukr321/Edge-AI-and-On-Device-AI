# Model Quantization — Tools & frameworks

| Tool | Ecosystem | Notes |
|---|---|---|
| TensorFlow Lite Converter | TF/Keras | PTQ (dynamic-range, full-integer, float16) and QAT via `tf.quantization` / `tensorflow_model_optimization` |
| PyTorch quantization (`torch.ao.quantization`) | PyTorch | Eager-mode and FX-graph-mode PTQ/QAT; dynamic quantization for RNN/Transformer layers |
| ExecuTorch | PyTorch | Meta's on-device inference runtime, successor path for deploying quantized PyTorch models to mobile/edge |
| ONNX Runtime quantization | ONNX | `onnxruntime.quantization` toolkit for static/dynamic PTQ across ONNX graphs, hardware-vendor-agnostic |
| bitsandbytes | Hugging Face / PyTorch | 8-bit and 4-bit (NF4) weight quantization for LLMs, used with QLoRA fine-tuning |
| GPTQ | LLMs | Post-training weight-only quantization using layer-wise second-order (Hessian) error correction, typically 3–4 bit |
| AWQ (Activation-aware Weight Quantization) | LLMs | Protects a small fraction of "salient" weight channels (identified by activation magnitude) from aggressive quantization |
| llama.cpp / GGUF | LLMs (CPU/edge) | Ships a family of quantization levels (Q8_0, Q5_K_M, Q4_K_M, Q4_0, Q3_K_M, Q2_K, etc.) trading size/speed against perplexity; "K-quants" mix precision within a tensor block for a better accuracy/size curve than naive uniform quantization |
