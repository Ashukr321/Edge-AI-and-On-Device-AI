# Core ML — Core workflow: convert → optimize → deploy

1. **Train** the model in PyTorch or TensorFlow (or use Create ML for supported task types with no external training).
2. **Convert with coremltools**:
   ```python
   import coremltools as ct
   mlmodel = ct.convert(torch_model, inputs=[ct.TensorType(shape=(1, 3, 224, 224))])
   mlmodel.save("MyModel.mlpackage")
   ```
   `ct.convert` accepts traced/scripted PyTorch models, TensorFlow SavedModels/Keras models, and ONNX (via the ONNX conversion path in older versions; direct PyTorch tracing is now the primary path).
3. **Set metadata** — input/output descriptions, preprocessing (mean/std normalization, image scaling) baked into the model spec via `ct.ImageType`, class labels for classifiers, and author/license info.
4. **Optimize** — apply post-training quantization or palettization via `coremltools.optimize.coreml` (e.g. `linear_quantize_weights`, `palettize_weights`), or quantization-aware training utilities for PyTorch before conversion when accuracy loss must be minimized.
5. **(Optional) Encrypt** the model for App Store distribution using Xcode's model encryption feature, generating an encryption key managed through App Store Connect.
6. **Integrate into Xcode** — drag the `.mlpackage` into the project; Xcode auto-generates a strongly-typed Swift/Objective-C interface class from the model's input/output spec.
7. **Run inference** via the generated class directly, or route image/video/text through the **Vision** / **Natural Language** frameworks, which wrap Core ML models with standard pre/post-processing for common CV/NLP tasks.
8. **Profile** using Xcode's Core ML Performance Report to confirm which compute unit each layer actually ran on and where latency is concentrated.
