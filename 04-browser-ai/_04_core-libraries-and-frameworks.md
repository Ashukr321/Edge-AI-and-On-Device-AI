# Browser AI: Running Machine Learning Client-Side — Core libraries & frameworks

- **TensorFlow.js** — Google's JS ML library; supports WebGL, WASM, and WebGPU backends; ships pretrained models for pose estimation, object detection, and NLP (via `@tensorflow-models/*`).
- **ONNX Runtime Web** — Microsoft's ONNX Runtime compiled to WASM/WebGPU; runs arbitrary ONNX-exported models (PyTorch, scikit-learn via skl2onnx, etc.) with execution providers (`wasm`, `webgpu`, `webgl`).
- **Transformers.js** — Hugging Face's port of the `transformers` library to the browser, built on ONNX Runtime Web; gives one-line access to thousands of Hugging Face Hub models (text classification, translation, embeddings, ASR via Whisper, image classification) with a familiar `pipeline()` API.
- **WebLLM (MLC-LLM project)** — runs full LLMs (Llama, Mistral, Phi, Gemma, Qwen, etc.) entirely in-browser on top of WebGPU, with an OpenAI-compatible chat-completion JS API. Useful for local chat assistants with no backend.
- **MediaPipe Web (Tasks API)** — Google's MediaPipe Solutions for web: face landmark detection, hand tracking, gesture recognition, image segmentation/background removal, audio classification — optimized C++/WASM cores with a thin JS wrapper.
- **WebDNN, ml5.js** — older/higher-level wrappers, less actively used today than the above.
