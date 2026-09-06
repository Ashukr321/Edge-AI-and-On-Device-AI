# Android Edge AI — Performance/optimization tips

- Always ship an explicit delegate fallback chain (vendor delegate → NNAPI/GPU → CPU); don't assume GPU/NPU delegate creation succeeds.
- Use `benchmark_model` (LiteRT's CLI tool) via `adb` on target devices before committing to a delegate strategy.
- Check `CompatibilityList` before instantiating a GPU delegate — creating one on an unsupported device can throw or silently underperform.
- Keep the interpreter/session alive across calls (don't recreate per inference); delegate setup is the expensive part.
- Use Play Feature Delivery conditional/on-demand modules for models beyond a few MB to keep base APK size down.
- Test AICore/Gemini Nano-dependent features with the availability check and a designed fallback — it isn't present on every device.
