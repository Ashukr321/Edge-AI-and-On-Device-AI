# On-Device AI — Constraints

- **Memory**: mobile RAM is shared with the OS and other apps; a model
  and its activation buffers must fit in a much smaller budget than a
  server GPU's dozens of GB of VRAM.
- **Battery**: every extra joule per inference reduces battery life;
  background/always-on models (e.g. wake-word detection) must run at
  near-idle power draw.
- **Thermal throttling**: sustained heavy inference (e.g. video processing)
  can trigger thermal throttling, degrading performance mid-session.
- **App size budgets**: app stores and users are sensitive to install
  size; bundling large model weights conflicts with this (mitigated by
  on-demand resource downloads, or OS-provided shared models).
- **OS/driver fragmentation**: accelerator availability and behavior
  varies across chip generations and OS versions, requiring fallback
  paths to CPU/GPU.
- **Storage and versioning**: multiple models bundled per app for
  different features add up in storage; over-the-air model updates need
  careful versioning independent of app releases.
