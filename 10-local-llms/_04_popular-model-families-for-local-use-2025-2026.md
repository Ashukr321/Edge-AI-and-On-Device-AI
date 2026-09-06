# Local LLMs — Popular model families for local use (2025-2026)

| Family | Notable sizes | Notes |
|---|---|---|
| Llama 3.x / 3.1 / 3.2 (Meta) | 1B, 3B, 8B, 70B, 405B | 3.2 added small 1B/3B models tuned for edge/mobile; 8B is the sweet spot for consumer GPUs |
| Mistral / Mixtral (Mistral AI) | 7B (Mistral), 8x7B / 8x22B (Mixtral MoE) | Mixtral needs full MoE weights in memory despite sparse compute |
| Phi-3 / Phi-4 (Microsoft) | 3.8B (mini), 14B | Trained on curated/synthetic data for strong reasoning-per-parameter, good CPU/edge fit |
| Gemma 2 / Gemma 3 (Google) | 2B, 9B, 27B (Gemma 2); 1B, 4B, 12B, 27B (Gemma 3, some multimodal) | Efficient architecture, permissive-ish license, good small-model quality |
| Qwen 2.5 (Alibaba) | 0.5B up to 72B, plus MoE variants | Strong multilingual and coding variants (Qwen2.5-Coder) |
| DeepSeek (R1 distills, V-series) | 1.5B-70B distilled variants | Distilled reasoning models popular for local use since early 2025 |
