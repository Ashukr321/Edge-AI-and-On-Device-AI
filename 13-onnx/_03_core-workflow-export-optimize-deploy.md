# ONNX & ONNX Runtime — Core workflow: export → optimize → deploy

1. **Train** the model in PyTorch, TensorFlow, scikit-learn, etc.
2. **Export to ONNX**
   - PyTorch: `torch.onnx.export(...)` (TorchDynamo-based exporter is the current default in recent PyTorch versions; the older TorchScript-based tracer still exists for legacy cases).
   - TensorFlow/Keras: via `tf2onnx`.
   - scikit-learn: via `skl2onnx`.
3. **Validate** the exported graph — run the same input through the original framework and through ORT, and diff outputs numerically (`onnxruntime` vs. PyTorch outputs, checking max abs/relative error).
4. **Optimize / quantize** (optional but common):
   - Graph optimizations (constant folding, node fusion, layout transforms) — ORT applies many of these automatically at load time, or you can pre-bake them offline with `onnxruntime.transformers.optimizer` or the ORT graph optimization API.
   - Quantization to INT8/INT4 or FP16 using the `onnxruntime.quantization` toolkit (dynamic quantization, static/post-training quantization with calibration data, or QAT-exported graphs).
5. **Deploy** by loading the `.onnx` file into an `InferenceSession` on the target device, selecting the appropriate Execution Provider(s).
6. **(Mobile/edge)** optionally convert to the **ORT format** (`.ort`), a serialized, pre-optimized flatbuffer used by ONNX Runtime Mobile to cut binary size and load time on phones/embedded devices.
