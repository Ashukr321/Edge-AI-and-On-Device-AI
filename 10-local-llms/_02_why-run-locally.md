# Local LLMs — Why run locally

- **Privacy**: prompts and data never leave the device — important for regulated industries, personal data, or proprietary code.
- **Cost**: no per-token billing; the marginal cost of an extra request is electricity.
- **Offline availability**: works on a plane, in the field, or in air-gapped environments.
- **Latency**: no network hop; for small models on a good GPU, time-to-first-token can beat a remote API.
- **Control**: pin a model version indefinitely, fine-tune it, inspect/modify weights, avoid provider-side deprecations or policy changes.

Trade-offs against hosted APIs: generally lower ceiling on raw capability versus frontier closed models (GPT-5-class, Claude, Gemini), you own the ops burden (updates, drivers, disk space), and throughput/quality per watt is usually worse than a hosted service optimized at scale.
