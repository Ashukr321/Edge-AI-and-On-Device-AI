# ONNX & ONNX Runtime — Key concepts

| Term | Meaning |
|---|---|
| **Opset** | A versioned set of operator definitions (e.g. opset 17, 18, 20). Exporting targets a specific opset; the runtime must support it. Newer opsets add/refine ops (e.g. better quantization ops, scaled-dot-product-attention). |
| **IR version** | The version of the ONNX file format/graph structure itself, separate from opset version. |
| **Graph / Node / Initializer** | A model is a DAG of `Node`s (operators); `Initializer`s are the baked-in weights; inputs/outputs carry named `ValueInfo` with shape/dtype. |
| **Dynamic axes** | Shape dimensions (e.g. batch size, sequence length) left symbolic at export time so the same graph serves varying input sizes. |
| **Custom ops / domains** | Operators outside the standard ONNX domain (e.g. `com.microsoft`, contributed ops), often needed for ops a framework has that ONNX doesn't natively define. |
| **Execution Provider (EP)** | ORT's plugin abstraction for a hardware/software backend (CPU, CUDA, TensorRT, DirectML, CoreML, NNAPI, etc.). ORT partitions the graph and dispatches subgraphs to whichever EP can run them. |
