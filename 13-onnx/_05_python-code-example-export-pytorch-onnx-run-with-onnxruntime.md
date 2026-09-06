# ONNX & ONNX Runtime — Python code example: export PyTorch → ONNX, run with onnxruntime

```python
import torch
import torch.nn as nn
import onnxruntime as ort
import numpy as np

class TinyNet(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc1 = nn.Linear(784, 128)
        self.fc2 = nn.Linear(128, 10)

    def forward(self, x):
        x = torch.relu(self.fc1(x))
        return self.fc2(x)

model = TinyNet().eval()
dummy_input = torch.randn(1, 784)

# 1. Export to ONNX
torch.onnx.export(
    model,
    dummy_input,
    "tiny_net.onnx",
    input_names=["input"],
    output_names=["logits"],
    dynamic_axes={"input": {0: "batch"}, "logits": {0: "batch"}},
    opset_version=18,
)

# 2. Load and run with ONNX Runtime
providers = ["CUDAExecutionProvider", "CPUExecutionProvider"]  # tries CUDA, falls back to CPU
session = ort.InferenceSession("tiny_net.onnx", providers=providers)

x = np.random.randn(4, 784).astype(np.float32)
outputs = session.run(
    output_names=["logits"],
    input_feed={"input": x},
)
print(outputs[0].shape)  # (4, 10)
print("Active EP:", session.get_providers())
```
