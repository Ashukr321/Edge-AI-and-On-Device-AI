# Local Speech Models — Speech-to-text (ASR)

- **Whisper** (OpenAI) — open-weight, multilingual ASR trained on ~680k hours of audio; ships in sizes tiny (39M), base (74M), small (244M), medium (769M), and large-v2/v3 (~1.5B). The most accurate general-purpose open ASR option, widely used offline via `whisper.cpp`.
- **whisper.cpp** (ggml-org) — a C/C++ port of Whisper for CPU/GPU inference without a Python/PyTorch dependency, with quantization support; the de facto way to run Whisper efficiently on a laptop, Raspberry Pi, or phone.
- **faster-whisper** — a CTranslate2-based reimplementation offering significantly faster inference than the original PyTorch implementation on CPU/GPU, while staying in the Python ecosystem.
- **Vosk** (Alpha Cephei) — a lightweight, streaming-capable offline ASR toolkit with small per-language models (as small as ~50MB), popular for embedded/streaming use where Whisper's compute cost is too high.
- **On-device OS-level ASR** — iOS's `SFSpeechRecognizer` (on-device mode since iOS 13) and Android's on-device Speech Recognition API/Gboard voice typing provide system-integrated offline dictation without bundling your own model.
