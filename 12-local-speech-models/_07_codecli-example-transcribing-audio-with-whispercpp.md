# Local Speech Models — Code/CLI example: transcribing audio with whisper.cpp

```bash
# Build whisper.cpp and download a model
git clone https://github.com/ggml-org/whisper.cpp
cd whisper.cpp
cmake -B build && cmake --build build --config Release
./models/download-ggml-model.sh base.en

# Transcribe a local audio file
./build/bin/whisper-cli -m models/ggml-base.en.bin -f recording.wav
```

Output includes timestamped segments, e.g.:

```
[00:00:00.000 --> 00:00:04.200]   Welcome to the on-device speech overview.
```

Streaming/live microphone transcription is available via the `whisper-stream` example built alongside `whisper-cli`.
