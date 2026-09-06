# llama.cpp — Building from source

```bash
git clone https://github.com/ggml-org/llama.cpp
cd llama.cpp

# CPU-only build
cmake -B build
cmake --build build --config Release -j

# CUDA build
cmake -B build -DGGML_CUDA=ON
cmake --build build --config Release -j
```

Prebuilt binaries are also published on GitHub Releases for common platforms, and it's packaged in Homebrew (`brew install llama.cpp`).
