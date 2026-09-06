# Local LLMs — Trade-offs summary

- **Quality vs. size**: smaller quantized models are faster and cheaper but noticeably weaker at multi-step reasoning, long-context recall, and instruction-following edge cases than frontier hosted models.
- **Aggressive quantization** (Q2/Q3) saves memory but can visibly degrade output quality, especially for smaller base models where there's less redundancy to compress away.
- **Ops burden**: you manage updates, security patches, disk space (models are multi-GB files), and driver compatibility yourself.
- **No built-in safety/moderation layer** — open local models generally ship without the guardrails a hosted API enforces server-side.
