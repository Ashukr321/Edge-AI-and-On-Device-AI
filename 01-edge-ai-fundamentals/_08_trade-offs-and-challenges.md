# Edge AI Fundamentals — Trade-offs & challenges

- Accuracy vs. footprint: aggressive compression can degrade accuracy,
  especially on edge cases and long-tail inputs.
- Fragmented hardware/software ecosystem: every accelerator vendor has its
  own SDK, operator support list, and quantization quirks.
- Testing at scale: validating a model across many device models, OS
  versions, and thermal conditions is much harder than testing one cloud
  server config.
- Update/versioning complexity: pushing model updates to millions of
  disconnected devices safely (rollback, staged rollout) is non-trivial.
- Security: models and data on-device are more exposed to extraction/
  tampering than a locked-down cloud server.
