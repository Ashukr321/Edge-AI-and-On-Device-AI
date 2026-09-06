# WebAssembly (WASM) for Edge & On-Device AI — Conceptual build flow: Rust → WASM (wasm-pack)

```bash
# 1. Write inference/pre-processing logic in Rust (e.g., tokenization, a small model, tensor ops)
cargo new my-inference-lib --lib

# 2. Add wasm-bindgen for JS interop, build with wasm-pack targeting the web
cargo add wasm-bindgen
wasm-pack build --target web

# Output: pkg/my_inference_lib_bg.wasm + a JS glue module for import in the browser
```

```js
// 3. Use the generated module directly in a web page
import init, { run_inference } from './pkg/my_inference_lib.js';

await init(); // instantiates the .wasm module
const result = run_inference(inputData);
```
