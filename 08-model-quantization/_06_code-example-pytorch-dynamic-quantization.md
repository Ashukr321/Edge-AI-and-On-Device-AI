# Model Quantization — Code example — PyTorch dynamic quantization

```python
import torch
from torch import nn
from torch.ao.quantization import quantize_dynamic

class SimpleClassifier(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc1 = nn.Linear(768, 256)
        self.relu = nn.ReLU()
        self.fc2 = nn.Linear(256, 10)

    def forward(self, x):
        return self.fc2(self.relu(self.fc1(x)))

model = SimpleClassifier()
model.eval()

# Dynamic quantization: weights of Linear layers -> int8,
# activations quantized on the fly at inference.
quantized_model = quantize_dynamic(
    model,
    {nn.Linear},          # which layer types to quantize
    dtype=torch.qint8,
)

print(f"Float32 size:  {sum(p.numel() * 4 for p in model.parameters()) / 1024:.1f} KB")
# Quantized modules replace weight storage with int8 tensors + scale/zero-point
torch.save(quantized_model.state_dict(), "model_int8.pt")
```
