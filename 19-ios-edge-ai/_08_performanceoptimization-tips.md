# iOS Edge AI — Performance/optimization tips

- Set `computeUnits` deliberately when a model doesn't benefit from ANE partitioning overhead (e.g., very small models) — `.all` isn't always fastest for tiny models due to unit-switching overhead.
- Use static/fixed input shapes where possible; flexible shapes can prevent full ANE compilation of a layer.
- Palettize/quantize large models — ANE benefits significantly from INT8/INT4 weights and lower memory bandwidth.
- Batch preprocessing (resize/normalize) using `Vision`/`Accelerate` rather than hand-rolled Swift loops.
- Reuse a single `MLModel`/prediction pipeline instance across calls; avoid reloading and recompiling per inference.
- Profile with **Xcode Instruments'** Core ML and Neural Engine instrument templates to see actual per-layer compute-unit placement and timing — this is the authoritative way to confirm ANE utilization rather than assuming it from `computeUnits` settings.
