# Browser AI: Running Machine Learning Client-Side — Trade-offs & browser support caveats

- Built-in AI APIs (Prompt API, Summarizer, Translator) are **Chromium-only** today; Firefox and Safari have no equivalent shipped, so cross-browser apps still need a bundled-model fallback (e.g., Transformers.js).
- WebGPU support is strong in Chrome/Edge, shipped in Firefox, and available in Safari (macOS/iOS) as of recent versions — but older browsers and some Linux/driver combos still fall back to WebGL/WASM.
- WebNN is still experimental/behind flags in most browsers as of 2025–2026; treat it as forward-looking, not production-ready everywhere.
- Large models mean large first-load downloads; always show progress and consider a "Wi-Fi only" download gate on mobile.
- No guaranteed background execution — a backgrounded/closed tab stops inference; this isn't a substitute for a real background service.
