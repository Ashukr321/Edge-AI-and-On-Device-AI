# WebGPU for Machine Learning — Current limitations

- **Browser support**: shipped in Chrome/Edge (desktop and Android) and Firefox; available in Safari on recent macOS/iOS versions — but version-gating and platform gaps remain, so feature-detect (`if (!navigator.gpu)`) and always provide a WASM/WebGL fallback path.
- **Driver/OS variance**: behavior and performance differ across Vulkan/Metal/Direct3D 12 backends; some older GPUs or virtualized environments (some CI runners, some VMs) lack WebGPU support entirely.
- **No fp64**, limited `f16` support (behind an optional feature flag), and some numeric edge cases differ from native GPU compute.
- **Shader compilation stalls**: first-time pipeline creation can cause a visible hitch; frameworks mitigate this with pipeline caching where possible.
- **Debugging tooling** is less mature than native GPU debuggers, though browser DevTools (Chrome's WebGPU inspector, `chrome://gpu`) and validation layers help.
- **Security model** disallows some low-level control (e.g., no arbitrary pointer arithmetic across GPU/CPU) that native compute APIs allow, which occasionally limits optimization tricks.
