# Libraries & Packages (Most Used)

## Model runtimes

| Package | Use for | Notes |
|---|---|---|
| [`@huggingface/transformers`](https://github.com/huggingface/transformers.js) (Transformers.js) | Text classification, embeddings, translation, image classification/segmentation, speech-to-text (Whisper), small LLMs | Easiest starting point — same API as Python `transformers`, huge model hub, auto WebGPU/WASM backend |
| `onnxruntime-web` | Running any ONNX-exported model | Most flexible/lowest-level; you convert your own PyTorch/TF model to ONNX first (see [ONNX](../13-onnx/)) |
| `@tensorflow/tfjs` | TF/Keras models, custom training in-browser, existing TF.js model zoo (pose, hand, face landmarks) | Mature, big ecosystem, slightly heavier bundle |
| `@mlc-ai/web-llm` (WebLLM) | Running full chat LLMs (Llama, Phi, Qwen, Gemma) fully client-side with a ChatGPT-like API | Needs WebGPU; multi-GB downloads — plan caching carefully |
| `@xenova/transformers` | Legacy name for Transformers.js pre-HF takeover | Use `@huggingface/transformers` instead now |

## Vision / on-device CV specific

- **`@mediapipe/tasks-vision`** — Google's ready-made pipelines: face detection/landmarks, hand tracking, pose, object detection, image segmentation. Fastest way to ship common CV features without touching a model file yourself.
- **`onnxruntime-web`** + a YOLO/YOLOv8 ONNX export — for custom object detection.

## Audio

- Transformers.js `pipeline("automatic-speech-recognition", "Xenova/whisper-tiny.en")` for STT.
- Web Speech API (`SpeechRecognition`, `SpeechSynthesisUtterance`) — native browser API, zero download, use it first before reaching for a model (see [ponytail ladder](../README.md): native platform feature beats a library).

## Compute backend (usually picked automatically by the runtime, but good to know)

- **WebGPU** — fastest, best support in Chrome/Edge 2024+; check `navigator.gpu` before relying on it.
- **WASM + SIMD/threads** — universal fallback, good enough for small/medium models.
- **WebGL** — older fallback, TF.js still supports it for broad compatibility.
- **WebNN** — emerging native-acceleration API (see [Browser AI](../04-browser-ai/_06_webnn-web-neural-network-api.md)), not yet universally supported.

## Framework glue (optional, nice to have)

- `comlink` — makes Web Worker `postMessage` feel like a normal async function call; removes the boilerplate of a manual worker message protocol.
- `idb` — small wrapper over IndexedDB, useful if you cache models/results yourself instead of relying on the runtime's built-in cache.

## What NOT to add

Don't hand-roll a model format parser, a WebGPU pipeline, or a custom caching
layer — every item above already does that. Reach for a new package only when
one of these doesn't cover the case.
