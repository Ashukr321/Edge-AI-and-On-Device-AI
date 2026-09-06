# Mobile AI — Why mobile is a distinct edge target

Mobile devices share constraints with other edge targets (limited compute, no guaranteed connectivity) but add a few of their own:

- **Battery budget** — inference competes with everything else drawing from a single cell that must last a day. A model that is "fast enough" on a bench with a wall adapter can still be rejected for draining battery too quickly in real use.
- **Thermal throttling** — phones have no fans. Sustained heavy inference (e.g., continuous video segmentation) raises SoC temperature until the OS throttles CPU/GPU/NPU clocks, silently degrading throughput mid-session.
- **App size limits** — app stores impose size ceilings and cellular-download caps (historically ~150-200MB before requiring Wi-Fi on Android; Apple has its own cellular download thresholds). A bundled multi-hundred-MB model can push an app over these limits.
- **Extreme hardware diversity** — unlike a fixed console or a controlled server fleet, "Android" spans thousands of SoC/GPU/NPU combinations from Qualcomm, MediaTek, Samsung Exynos, Google Tensor, and more, each with different driver quality and supported ops. iOS is more homogeneous but still spans several Neural Engine generations.
- **OS lifecycle interruptions** — apps get backgrounded, suspended, or killed mid-inference; models must checkpoint or gracefully abandon work.
- **User-facing latency expectations** — camera and keyboard features are expected to respond in tens of milliseconds, not seconds.
