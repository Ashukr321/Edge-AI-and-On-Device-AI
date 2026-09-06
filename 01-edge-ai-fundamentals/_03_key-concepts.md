# Edge AI Fundamentals — Key concepts

- **Inference vs. training**: Edge AI is overwhelmingly about *inference*.
  Training still typically happens in the cloud on aggregated data (with
  exceptions like federated learning and on-device fine-tuning/personalization).
- **Model compression**: Cloud-trained models are usually too large, too
  slow, or too power-hungry to run as-is on edge hardware, so they go
  through an optimization step before deployment.
- **Heterogeneous compute**: Edge devices mix general-purpose CPUs with
  specialized accelerators (GPU, NPU, DSP) that only some operators/layers
  can use efficiently.
- **Power and thermal budgets**: Unlike a data center, edge devices are
  often battery-powered or passively cooled, so operations-per-joule matters
  as much as raw throughput.
- **Determinism**: Many edge use cases (safety systems, control loops) need
  bounded, predictable latency, not just low average latency.
