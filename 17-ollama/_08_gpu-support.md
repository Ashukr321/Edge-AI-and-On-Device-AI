# Ollama — GPU support

Ollama auto-detects and uses available GPU acceleration without manual flag-setting: NVIDIA (CUDA), AMD (ROCm on Linux, and DirectML-backed support on Windows), and Apple Silicon (Metal) are all supported out of the box. It falls back to CPU automatically when no compatible GPU is found, and can partially offload layers when a model doesn't fully fit in VRAM — mirroring llama.cpp's `-ngl` behavior but chosen automatically rather than via a manual flag.
