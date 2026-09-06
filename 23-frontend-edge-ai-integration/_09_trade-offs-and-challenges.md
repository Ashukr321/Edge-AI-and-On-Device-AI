# Trade-offs & Challenges

- **Download size** — even a "small" model is often 20-500MB; first-visit experience needs a loading/progress state, and mobile data users may bounce.
- **Device variance** — a low-end phone may run 10x slower than a desktop with WebGPU; no way to guarantee a latency SLA like you could with a server.
- **Browser support gaps** — WebGPU and WebNN aren't universal yet; you need a WASM/WebGL fallback path (most runtimes handle this, but test it).
- **No server-side control** — you can't patch a bug in the model without shipping a new frontend deploy (vs. a backend API you can hotfix independently).
- **Bundle/CORS footguns** — self-hosting model files wrong (missing CORS/COOP/COEP headers) is the most common "works locally, breaks in prod" issue.
- **Not a fit for everything** — large/complex models (big LLMs, high-res diffusion) are still better served from the cloud; edge AI shines for small-to-medium models where privacy/offline/cost matter more than raw capability.
