# Browser AI: Running Machine Learning Client-Side — Overview

Browser AI refers to executing machine learning inference (and sometimes training) directly inside a web browser, on the user's own device, using JavaScript/WASM/GPU APIs rather than sending data to a server. The browser becomes the inference runtime: models are fetched once (or bundled/cached), loaded into memory, and run against WebGL, WebGPU, WebAssembly, or native accelerator backends exposed via the browser.

This sits at the intersection of Edge AI and the web platform: no app store, no install, cross-platform by default (desktop, mobile, any OS with a modern browser), and it inherits the web's sandboxing and permission model.
