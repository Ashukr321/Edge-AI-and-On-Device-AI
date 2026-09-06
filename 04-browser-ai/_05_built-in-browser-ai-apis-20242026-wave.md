# Browser AI: Running Machine Learning Client-Side — Built-in browser AI APIs (2024–2026 wave)

Chromium has been shipping **built-in AI** so pages can call a local model without downloading one themselves:

- **Prompt API** (`window.ai` / `LanguageModel` in Chrome, currently behind origin trials/experimental flags) — gives page JS a session against Chrome's on-device model, **Gemini Nano**, for free-form prompting.
- **Summarizer API**, **Translator API**, **Language Detector API**, **Writer/Rewriter API** — task-specific built-in APIs, each backed by a local model shipped with the browser, exposed as stable-ish web APIs (rolling out via Chrome's "Built-in AI" effort, some already stable in Chrome as of 2025, others still in origin trial).
- These avoid model download entirely (the model ships with the OS/browser), but are Chromium/Chrome-specific today — no cross-browser standard yet, and availability depends on device capability checks (`availability()`/`capabilities()` calls that can return `no`, `after-download`, or `readily`).
