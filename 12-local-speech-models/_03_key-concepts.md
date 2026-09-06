# Local Speech Models — Key concepts

- **ASR (Automatic Speech Recognition)**: audio-to-text; modern models are typically encoder-decoder transformers (Whisper) or CTC/streaming variants (Vosk, wav2vec2-based).
- **Streaming vs. batch transcription**: batch models process a full audio clip at once (higher accuracy, some latency); streaming models emit partial text as audio arrives (lower latency, used for live captions/dictation).
- **Wake word / keyword spotting (KWS)**: a tiny, always-running classifier listening for one specific phrase, deliberately kept small (tens to hundreds of KB) to run continuously at negligible power.
- **Neural TTS**: text-to-speech using a neural vocoder/acoustic model pipeline (as opposed to older formant/concatenative synthesis), producing natural-sounding voices; on-device neural TTS became standard on iOS and Android in the last few years.
- **Diarization**: identifying "who spoke when" in multi-speaker audio — often bundled into meeting-transcription pipelines alongside ASR.
- **WER (Word Error Rate)**: the standard ASR accuracy metric — percentage of words inserted, deleted, or substituted versus a reference transcript.
