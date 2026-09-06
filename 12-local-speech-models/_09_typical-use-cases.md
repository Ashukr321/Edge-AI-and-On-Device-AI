# Local Speech Models — Typical use cases

- **Offline voice assistants**: wake word (Porcupine/openWakeWord) → ASR (whisper.cpp/Vosk) → local or remote LLM for response → TTS (Piper) — a fully local pipeline used in privacy-focused smart-speaker projects.
- **Dictation**: real-time or near-real-time speech-to-text for writing, common in accessibility tools and note-taking apps.
- **Meeting transcription**: batch transcription of recorded meetings, often paired with diarization to attribute text to speakers, run locally for confidentiality.
- **Embedded voice control**: microcontroller-class keyword spotting for appliances, wearables, and hearables where cloud connectivity isn't available or desired.
