# Local Speech Models — Latency/accuracy trade-offs (Whisper model sizes)

| Model | Parameters | Relative speed | Typical use |
|---|---|---|---|
| tiny | 39M | Fastest (real-time+ even on modest CPUs) | Quick captions, low-power devices, draft transcripts |
| base | 74M | Very fast | Good default for lightweight offline dictation |
| small | 244M | Moderate | Better accuracy for noisy/accented audio, still laptop-friendly |
| medium | 769M | Slower, usually needs a GPU or patience on CPU | Meeting transcription where accuracy matters more than speed |
| large-v3 | ~1.5B | Slowest, GPU strongly recommended | Best accuracy, professional transcription, hard audio (multiple accents, background noise) |

English-only variants (`.en` suffix, tiny through medium) are slightly more accurate than multilingual ones for English audio specifically. Quantized whisper.cpp builds (Q5/Q8 GGML) shrink memory further with modest accuracy loss.
