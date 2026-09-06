# ONNX & ONNX Runtime — Overview

ONNX (Open Neural Network Exchange) is an open, interoperable format for representing machine learning models. It defines a common computation-graph representation (operators, tensors, data types, control flow) so a model trained in one framework can be exported once and executed by many different runtimes and hardware backends without being rewritten.

ONNX itself is just a spec + protobuf schema — it does not run models. **ONNX Runtime (ORT)** is Microsoft's open-source, cross-platform inference engine that consumes `.onnx` graphs and executes them efficiently on CPUs, GPUs, NPUs, mobile SoCs, and the browser (via WASM/WebGPU). Together, "export to ONNX, run with ORT" is one of the most common paths for taking a PyTorch/TensorFlow model to production and to the edge.
