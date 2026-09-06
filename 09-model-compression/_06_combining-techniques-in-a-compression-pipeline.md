# Model Compression — Combining techniques in a compression pipeline

A representative end-to-end pipeline for deploying a large model to an edge device:

1. Start from (or search for, via NAS) an efficient base architecture (e.g. MobileNetV3, DistilBERT).
2. Optionally distill from a larger, more accurate teacher to recover accuracy at the smaller model's scale.
3. Prune the resulting model (structured pruning if hardware has no sparse kernel support), fine-tuning after each pruning round.
4. Apply quantization (PTQ or QAT) as the final step, since quantizing a smaller/pruned model further reduces already-reduced memory and compute.
5. Compile/export for the target runtime (TensorFlow Lite, ONNX Runtime, TensorRT, CoreML) and benchmark accuracy/latency/power on real target hardware, not just in simulation.
