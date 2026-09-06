# Architecture Patterns

## 1. Client-only (fully in-browser)

```
Browser
 ├─ UI (React/Vue/Svelte/vanilla)
 ├─ Model runtime (Transformers.js / ONNX Runtime Web / TF.js / WebLLM)
 ├─ Model weights (fetched once from CDN, cached in Cache Storage/IndexedDB)
 └─ Compute backend: WebGPU → WASM+SIMD → WebGL (fallback chain)
```
No server involved in inference at all. Best for: image/text classification,
background removal, in-browser chat with a small LLM, embeddings for
client-side search.

## 2. Hybrid (edge-first, cloud fallback)

```
Browser → tries local model first
   ├─ success → done, no network call
   └─ fails / device too weak / model too large
        → falls back to a cloud API (OpenAI/Anthropic/your backend)
```
Best for: apps that must work on low-end devices too, or where accuracy
matters more than the offline guarantee. Feature-detect WebGPU/device memory
and route accordingly.

## 3. Worker-offloaded (keep the UI thread free)

```
Main thread (UI) ⇄ postMessage ⇄ Web Worker (model load + inference)
```
Model loading and inference are CPU/GPU heavy and block the main thread if
run there — always run them in a Web Worker (or a library's built-in worker
mode, e.g. Transformers.js's `pipeline` in a worker) so scrolling/typing stay
smooth.

## 4. Progressive / cached delivery

```
1st visit:  fetch weights from CDN → cache in Cache Storage → run
later visit: read from cache (instant) → run
```
Register a Service Worker that caches model files with a cache-first
strategy, since weights are large (10s–100s of MB) and immutable per version.

## 5. Native wrapper (Capacitor/React Native/Electron)

Same in-browser AI code, shipped inside a WebView-based native shell when you
need app-store distribution — the model/runtime code doesn't change, only the
packaging does. See [Mobile AI](../03-mobile-ai/) if you want true native
(Core ML/TFLite) instead of a WebView.
