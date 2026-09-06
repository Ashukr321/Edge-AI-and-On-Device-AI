# Project Ideas

## Beginner
- **Background remover** — Transformers.js image-segmentation model, drag-and-drop UI, download the cutout PNG.
- **Sentiment/toxicity checker for a comment box** — text-classification pipeline, runs as-you-type.
- **Live webcam pose/hand tracker** — MediaPipe Tasks Vision, overlay landmarks on a `<canvas>`.

## Intermediate
- **In-browser semantic search** — embed a set of documents client-side (feature-extraction pipeline), cosine-similarity search, no vector DB/server needed for small corpora.
- **Voice memo transcriber** — record audio (`MediaRecorder`), transcribe with Whisper via Transformers.js, fully offline after first load.
- **Smart image gallery tagger** — run image classification on every uploaded photo, auto-tag and make them filterable.

## Advanced
- **Offline chat assistant** — WebLLM running a small quantized model (e.g. Phi-3-mini or Llama-3.2-1B), full chat UI, works with no network after model download.
- **Real-time object detection overlay** — YOLOv8n exported to ONNX, `onnxruntime-web` + WebGPU, live webcam bounding boxes.
- **Hybrid edge/cloud assistant** — try a local small model first, fall back to a cloud LLM API for complex queries, based on a confidence/complexity heuristic.

## Real-life products already doing this (proof it's not just a toy)

| Product | What it uses edge AI for |
|---|---|
| Google Meet / Zoom web | Background blur/replacement, noise suppression — runs client-side so it scales to millions of calls with no server GPU cost |
| Figma | On-canvas smart features (e.g. auto-layout suggestions) increasingly run client-side to stay instant while editing |
| Notion AI / Grammarly (browser extension) | Lightweight grammar/tone checks run locally as-you-type, only heavier rewrites go to the cloud — a real hybrid pattern |
| Adobe Photoshop (web) | Client-side background removal / object selection previews before committing to a full server-side render |
| Duolingo | On-device speech recognition for pronunciation exercises — instant feedback, no round trip per attempt |
| Google Photos (web) | Face grouping / object search previews computed client-side before syncing |

## Real-world use cases mapped to project ideas above

- **Customer support widget** that classifies ticket sentiment/urgency client-side before it even hits your backend queue → triage faster, cheaper (maps to the sentiment checker idea).
- **Telehealth or field-service PWA** used in low-connectivity areas (rural clinics, construction sites) → offline voice transcription for notes (maps to the voice memo transcriber idea).
- **E-commerce product photo tool** for sellers uploading listings → instant background removal/tagging before upload, no wait on a server job queue (maps to background remover + gallery tagger).
- **Internal support/knowledge-base search** for a company wiki with a few hundred docs → in-browser semantic search, no vector DB infra to stand up or pay for.
- **Accessibility tool embedded in a public-facing site** → live captioning/webcam sign-language landmark tracking that must work instantly and privately, no user video ever uploaded.
- **Retail/kiosk app on unreliable in-store WiFi** → real-time object/shelf detection overlay that can't depend on network uptime.
- **Personal-finance or journaling app** → local LLM chat assistant for reflecting on private entries, marketed specifically on "your data never leaves your device."

For the broader (non-frontend-specific) project list, see
[Edge AI Projects](../22-edge-ai-projects/).
