# Local Speech Models — Hardware requirements

| Component | Typical footprint | Hardware |
|---|---|---|
| Wake word (KWS) | tens-hundreds of KB | Microcontroller / always-on DSP, negligible power |
| Whisper tiny/base | ~75-150 MB (fp16) | Phone CPU, Raspberry Pi, any modern laptop |
| Whisper small/medium | ~500MB-1.5GB | Laptop CPU (usable) or entry GPU (comfortable) |
| Whisper large-v3 | ~3 GB | GPU with 6GB+ VRAM recommended for real-time-ish speed |
| Piper TTS voice | 20-100 MB per voice | Runs real-time on Raspberry Pi-class hardware |
