# Local Speech Models — Trade-offs

- Smaller Whisper models are fast enough for real-time captioning but produce noticeably more errors on accented speech, background noise, or domain-specific vocabulary.
- Streaming ASR (Vosk, streaming Whisper variants) sacrifices some accuracy versus full-utterance batch decoding, since the model has less future context to disambiguate words.
- Wake-word engines trade generality for efficiency — they detect one (or a few) fixed phrases extremely efficiently rather than general speech.
- On-device neural TTS voices are typically fewer and less customizable than large cloud TTS catalogs, though quality has converged significantly.
