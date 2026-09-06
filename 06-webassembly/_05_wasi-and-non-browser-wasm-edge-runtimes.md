# WebAssembly (WASM) for Edge & On-Device AI — WASI and non-browser WASM edge runtimes

Outside the browser, WASM is used as a lightweight, fast-starting, sandboxed alternative to containers for edge and serverless deployment:

- **Wasmtime** — the reference standalone WASM runtime (from the Bytecode Alliance), embeddable in Rust/C/Python/.NET hosts; implements WASI for file/network access outside a browser sandbox.
- **Wasmer** — another standalone WASM runtime with a package registry (WAPM) and multi-language embedding SDKs.
- **Edge/CDN platforms** (e.g., Cloudflare Workers, Fastly Compute) run WASM modules per-request with millisecond cold-starts, far faster than spinning up a container — attractive for lightweight inference (small classifiers, feature extraction, tokenization) at the network edge, close to users.
- These runtimes let a single WASM-compiled inference module be deployed identically in a browser tab, a CDN edge node, or an embedded/IoT Linux device running Wasmtime — genuine "compile once, run anywhere" for edge AI.
