# iOS Edge AI — Hardware acceleration

- **CPU**: fallback and best for control-flow-heavy or unsupported-op sections of a graph.
- **GPU**: Metal-backed, used for compute-heavy but less regular workloads.
- **Apple Neural Engine (ANE)**: highest efficiency for supported convolution/attention-heavy ops; Core ML's compiler decides per-layer placement when `computeUnits` is `.all`, so model architecture choices (op types, tensor shapes/layouts) materially affect how much of the graph actually lands on ANE.
