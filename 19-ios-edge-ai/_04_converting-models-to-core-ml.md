# iOS Edge AI — Converting models to Core ML

`coremltools` is the standard path from a trained PyTorch or TensorFlow model to a deployable `.mlpackage`:

```python
import coremltools as ct
import torch

# Example: tracing a PyTorch model, then converting
model.eval()
example_input = torch.rand(1, 3, 224, 224)
traced_model = torch.jit.trace(model, example_input)

mlmodel = ct.convert(
    traced_model,
    inputs=[ct.ImageType(name="input", shape=example_input.shape)],
    convert_to="mlprogram",          # modern ML Program backend (vs. legacy neuralnetwork)
    compute_units=ct.ComputeUnit.ALL,  # let Core ML choose CPU/GPU/ANE
)

mlmodel.save("MyModel.mlpackage")
```

Key conversion considerations:

- Prefer the **ML Program** (`mlprogram`) backend over the legacy `neuralnetwork` backend — it's the actively developed format with better quantization and control-flow support.
- Apply post-training quantization/palettization with `coremltools.optimize` (linear quantization to INT8/INT4, weight palettization, pruning) to shrink size and improve ANE utilization.
- Validate outputs against the original PyTorch/TensorFlow model on representative inputs — some ops convert with subtly different numerics (especially normalization layers and custom ops), and unsupported ops may silently fall back to a slower compute unit or require a custom Core ML op.
