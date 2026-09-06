# Model Quantization — Per-tensor vs. per-channel quantization

- **Per-tensor**: a single scale (and zero-point) for the entire weight tensor. Simple, but a single outlier channel can force a wide range that degrades precision for every other channel.
- **Per-channel** (a.k.a. per-axis): a separate scale per output channel (typically per convolutional filter or per output neuron). Significantly better accuracy for CNNs and is the default approach in TensorFlow Lite and PyTorch's quantization backends for weights. Per-channel activation quantization is less common because activations don't have a fixed channel-aligned tensor layout across ops as cleanly as weights do.
