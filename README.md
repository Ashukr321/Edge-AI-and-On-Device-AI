# Edge AI and On-Device AI

A learning and reference repo covering AI that runs on-device and at the edge — from
microcontrollers to phones to the browser — instead of in the cloud.

## How this repo is organized

There are 23 numbered topic folders. Each folder holds **no README.md** — instead every
section of that topic is its own standalone Markdown file, prefixed with its reading
order (`_01_overview.md`, `_02_key-concepts.md`, ...) so the files sort and read
top-to-bottom in the order the topic is meant to be learned.

This root file is the only `README.md` in the repo — it explains the project and links
down to every topic file below, in reading order.

## Contents

### Foundations

**[Edge AI Fundamentals](01-edge-ai-fundamentals/)**
[Overview](01-edge-ai-fundamentals/_01_overview.md) · [Why it matters](01-edge-ai-fundamentals/_02_why-it-matters.md) · [Key concepts](01-edge-ai-fundamentals/_03_key-concepts.md) · [The edge AI pipeline](01-edge-ai-fundamentals/_04_the-edge-ai-pipeline.md) · [Typical hardware tiers](01-edge-ai-fundamentals/_05_typical-hardware-tiers.md) · [Core techniques](01-edge-ai-fundamentals/_06_core-techniques.md) · [Tools & frameworks](01-edge-ai-fundamentals/_07_tools-and-frameworks.md) · [Trade-offs & challenges](01-edge-ai-fundamentals/_08_trade-offs-and-challenges.md) · [Use cases](01-edge-ai-fundamentals/_09_use-cases.md) · [Further reading](01-edge-ai-fundamentals/_10_further-reading.md)

**[On-Device AI](02-on-device-ai/)**
[Overview](02-on-device-ai/_01_overview.md) · [Why it matters](02-on-device-ai/_02_why-it-matters.md) · [Key concepts](02-on-device-ai/_03_key-concepts.md) · [Hardware accelerators](02-on-device-ai/_04_hardware-accelerators.md) · [On-device inference engines](02-on-device-ai/_05_on-device-inference-engines.md) · [Constraints](02-on-device-ai/_06_constraints.md) · [Typical use cases](02-on-device-ai/_07_typical-use-cases.md) · [Trade-offs & challenges](02-on-device-ai/_08_trade-offs-and-challenges.md) · [Example: minimal TFLite on-device inference (Android/Kotlin-ish pseudocode)](02-on-device-ai/_09_example-minimal-tflite-on-device-inference-androidkotlin-ish-pseudocode.md) · [Further reading](02-on-device-ai/_10_further-reading.md)

**[Edge AI Architecture](20-edge-ai-architecture/)**
[Overview](20-edge-ai-architecture/_01_overview.md) · [Why it matters](20-edge-ai-architecture/_02_why-it-matters.md) · [End-to-end reference pipeline](20-edge-ai-architecture/_03_end-to-end-reference-pipeline.md) · [Hybrid edge-cloud architectures](20-edge-ai-architecture/_04_hybrid-edge-cloud-architectures.md) · [MLOps for edge](20-edge-ai-architecture/_05_mlops-for-edge.md) · [Tools & frameworks](20-edge-ai-architecture/_06_tools-and-frameworks.md) · [Trade-offs & challenges](20-edge-ai-architecture/_07_trade-offs-and-challenges.md) · [Further reading](20-edge-ai-architecture/_08_further-reading.md)

**[Cloud vs. Edge vs. Hybrid](21-cloud-vs-edge/)**
[Overview](21-cloud-vs-edge/_01_overview.md) · [Why it matters](21-cloud-vs-edge/_02_why-it-matters.md) · [Direct comparison](21-cloud-vs-edge/_03_direct-comparison.md) · [Decision framework](21-cloud-vs-edge/_04_decision-framework.md) · [Real-world examples](21-cloud-vs-edge/_05_real-world-examples.md) · [Trade-offs & challenges](21-cloud-vs-edge/_06_trade-offs-and-challenges.md) · [Further reading](21-cloud-vs-edge/_07_further-reading.md)

**[Edge AI Projects](22-edge-ai-projects/)**
[Overview](22-edge-ai-projects/_01_overview.md) · [Beginner](22-edge-ai-projects/_02_beginner.md) · [Intermediate](22-edge-ai-projects/_03_intermediate.md) · [Advanced](22-edge-ai-projects/_04_advanced.md) · [Trade-offs & challenges when doing these projects](22-edge-ai-projects/_05_trade-offs-and-challenges-when-doing-these-projects.md) · [Further reading](22-edge-ai-projects/_06_further-reading.md)


### Mobile

**[Mobile AI](03-mobile-ai/)**
[Overview](03-mobile-ai/_01_overview.md) · [Why mobile is a distinct edge target](03-mobile-ai/_02_why-mobile-is-a-distinct-edge-target.md) · [Key concepts](03-mobile-ai/_03_key-concepts.md) · [Frameworks & APIs](03-mobile-ai/_04_frameworks-and-apis.md) · [Model formats & deployment workflow](03-mobile-ai/_05_model-formats-and-deployment-workflow.md) · [Typical mobile AI features](03-mobile-ai/_06_typical-mobile-ai-features.md) · [Hardware acceleration](03-mobile-ai/_07_hardware-acceleration.md) · [Performance & optimization tips](03-mobile-ai/_08_performance-and-optimization-tips.md) · [Code example](03-mobile-ai/_09_code-example.md) · [Trade-offs & challenges](03-mobile-ai/_10_trade-offs-and-challenges.md) · [Further reading](03-mobile-ai/_11_further-reading.md)

**[Android Edge AI](18-android-edge-ai/)**
[Overview](18-android-edge-ai/_01_overview.md) · [Key concepts](18-android-edge-ai/_02_key-concepts.md) · [Frameworks & APIs](18-android-edge-ai/_03_frameworks-and-apis.md) · [NNAPI history and its deprecation](18-android-edge-ai/_04_nnapi-history-and-its-deprecation.md) · [Google Tensor, AICore, and Gemini Nano](18-android-edge-ai/_05_google-tensor-aicore-and-gemini-nano.md) · [Model formats / deployment workflow](18-android-edge-ai/_06_model-formats-deployment-workflow.md) · [Code example (Kotlin, loading a TFLite model)](18-android-edge-ai/_07_code-example-kotlin-loading-a-tflite-model.md) · [Hardware acceleration](18-android-edge-ai/_08_hardware-acceleration.md) · [Performance/optimization tips](18-android-edge-ai/_09_performanceoptimization-tips.md) · [Trade-offs & challenges](18-android-edge-ai/_10_trade-offs-and-challenges.md) · [Further reading](18-android-edge-ai/_11_further-reading.md)

**[iOS Edge AI](19-ios-edge-ai/)**
[Overview](19-ios-edge-ai/_01_overview.md) · [Key concepts](19-ios-edge-ai/_02_key-concepts.md) · [Frameworks & APIs](19-ios-edge-ai/_03_frameworks-and-apis.md) · [Converting models to Core ML](19-ios-edge-ai/_04_converting-models-to-core-ml.md) · [Model formats / deployment workflow](19-ios-edge-ai/_05_model-formats-deployment-workflow.md) · [Code example (Swift, loading a Core ML model)](19-ios-edge-ai/_06_code-example-swift-loading-a-core-ml-model.md) · [Hardware acceleration](19-ios-edge-ai/_07_hardware-acceleration.md) · [Performance/optimization tips](19-ios-edge-ai/_08_performanceoptimization-tips.md) · [Trade-offs & challenges](19-ios-edge-ai/_09_trade-offs-and-challenges.md) · [Further reading](19-ios-edge-ai/_10_further-reading.md)


### Browser / Web

**[Browser AI: Running Machine Learning Client-Side](04-browser-ai/)**
[Overview](04-browser-ai/_01_overview.md) · [Why run AI in the browser](04-browser-ai/_02_why-run-ai-in-the-browser.md) · [Key concepts](04-browser-ai/_03_key-concepts.md) · [Core libraries & frameworks](04-browser-ai/_04_core-libraries-and-frameworks.md) · [Built-in browser AI APIs (2024–2026 wave)](04-browser-ai/_05_built-in-browser-ai-apis-20242026-wave.md) · [WebNN (Web Neural Network API)](04-browser-ai/_06_webnn-web-neural-network-api.md) · [Typical use cases](04-browser-ai/_07_typical-use-cases.md) · [Code example: image classification with Transformers.js](04-browser-ai/_08_code-example-image-classification-with-transformersjs.md) · [Code example: running an ONNX model directly with ONNX Runtime Web](04-browser-ai/_09_code-example-running-an-onnx-model-directly-with-onnx-runtime-web.md) · [Performance considerations](04-browser-ai/_10_performance-considerations.md) · [Trade-offs & browser support caveats](04-browser-ai/_11_trade-offs-and-browser-support-caveats.md) · [Further reading](04-browser-ai/_12_further-reading.md)

**[WebGPU for Machine Learning](05-webgpu/)**
[Overview](05-webgpu/_01_overview.md) · [Why WebGPU matters for ML](05-webgpu/_02_why-webgpu-matters-for-ml.md) · [Key concepts](05-webgpu/_03_key-concepts.md) · [How frameworks use WebGPU](05-webgpu/_04_how-frameworks-use-webgpu.md) · [Minimal WebGPU setup example (JavaScript)](05-webgpu/_05_minimal-webgpu-setup-example-javascript.md) · [Minimal compute shader example (WGSL): element-wise vector add](05-webgpu/_06_minimal-compute-shader-example-wgsl-element-wise-vector-add.md) · [Performance: WebGPU vs. WebGL vs. WASM (qualitative)](05-webgpu/_07_performance-webgpu-vs-webgl-vs-wasm-qualitative.md) · [Current limitations](05-webgpu/_08_current-limitations.md) · [Further reading](05-webgpu/_09_further-reading.md)

**[WebAssembly (WASM) for Edge & On-Device AI](06-webassembly/)**
[Overview](06-webassembly/_01_overview.md) · [Why WASM for ML](06-webassembly/_02_why-wasm-for-ml.md) · [Key concepts](06-webassembly/_03_key-concepts.md) · [Use in ML frameworks](06-webassembly/_04_use-in-ml-frameworks.md) · [WASI and non-browser WASM edge runtimes](06-webassembly/_05_wasi-and-non-browser-wasm-edge-runtimes.md) · [Conceptual build flow: Rust → WASM (wasm-pack)](06-webassembly/_06_conceptual-build-flow-rust-wasm-wasm-pack.md) · [Conceptual build flow: C/C++ → WASM (Emscripten)](06-webassembly/_07_conceptual-build-flow-cc-wasm-emscripten.md) · [Performance considerations](06-webassembly/_08_performance-considerations.md) · [Trade-offs vs. native and vs. WebGPU](06-webassembly/_09_trade-offs-vs-native-and-vs-webgpu.md) · [Further reading](06-webassembly/_10_further-reading.md)

**[Frontend + Edge AI Integration](23-frontend-edge-ai-integration/)**
[Overview](23-frontend-edge-ai-integration/_01_overview.md) · [Why frontend devs should care](23-frontend-edge-ai-integration/_02_why-frontend-devs-should-care.md) · [Architecture patterns](23-frontend-edge-ai-integration/_03_architecture-patterns.md) · [Libraries & packages](23-frontend-edge-ai-integration/_04_libraries-and-packages.md) · [Build & deploy workflow](23-frontend-edge-ai-integration/_05_build-and-deploy-workflow.md) · [Project ideas](23-frontend-edge-ai-integration/_06_project-ideas.md) · [Code example](23-frontend-edge-ai-integration/_07_code-example.md) · [Performance & caching tips](23-frontend-edge-ai-integration/_08_performance-and-caching-tips.md) · [Trade-offs & challenges](23-frontend-edge-ai-integration/_09_trade-offs-and-challenges.md) · [Further reading](23-frontend-edge-ai-integration/_10_further-reading.md) · [When to use it, and when not to](23-frontend-edge-ai-integration/_11_when-to-use-and-when-not-to.md) · [Example live demos](23-frontend-edge-ai-integration/_12_example-live-demos.md)


### Model Optimization

**[TinyML](07-tinyml/)**
[Overview](07-tinyml/_01_overview.md) · [Key concepts](07-tinyml/_02_key-concepts.md) · [Target hardware](07-tinyml/_03_target-hardware.md) · [Frameworks](07-tinyml/_04_frameworks.md) · [TinyML deployment workflow](07-tinyml/_05_tinyml-deployment-workflow.md) · [Code example — minimal TFLite Micro inference loop (C++)](07-tinyml/_06_code-example-minimal-tflite-micro-inference-loop-c.md) · [Typical use cases](07-tinyml/_07_typical-use-cases.md) · [Trade-offs](07-tinyml/_08_trade-offs.md) · [Further reading](07-tinyml/_09_further-reading.md)

**[Model Quantization](08-model-quantization/)**
[Overview](08-model-quantization/_01_overview.md) · [Key concepts](08-model-quantization/_02_key-concepts.md) · [Post-training quantization (PTQ) vs. quantization-aware training (QAT)](08-model-quantization/_03_post-training-quantization-ptq-vs-quantization-aware-training-qat.md) · [Per-tensor vs. per-channel quantization](08-model-quantization/_04_per-tensor-vs-per-channel-quantization.md) · [Tools & frameworks](08-model-quantization/_05_tools-and-frameworks.md) · [Code example — PyTorch dynamic quantization](08-model-quantization/_06_code-example-pytorch-dynamic-quantization.md) · [Code example — TensorFlow Lite post-training full-integer quantization](08-model-quantization/_07_code-example-tensorflow-lite-post-training-full-integer-quantization.md) · [Trade-offs: accuracy vs. size/speed](08-model-quantization/_08_trade-offs-accuracy-vs-sizespeed.md) · [Further reading](08-model-quantization/_09_further-reading.md)

**[Model Compression](09-model-compression/)**
[Overview](09-model-compression/_01_overview.md) · [Key concepts](09-model-compression/_02_key-concepts.md) · [Techniques](09-model-compression/_03_techniques.md) · [Tools & frameworks](09-model-compression/_04_tools-and-frameworks.md) · [Code example — magnitude pruning + distillation loss (PyTorch)](09-model-compression/_05_code-example-magnitude-pruning-distillation-loss-pytorch.md) · [Combining techniques in a compression pipeline](09-model-compression/_06_combining-techniques-in-a-compression-pipeline.md) · [Trade-offs](09-model-compression/_07_trade-offs.md) · [Further reading](09-model-compression/_08_further-reading.md)


### Local Models & Runtimes

**[Local LLMs](10-local-llms/)**
[Overview](10-local-llms/_01_overview.md) · [Why run locally](10-local-llms/_02_why-run-locally.md) · [Key concepts](10-local-llms/_03_key-concepts.md) · [Popular model families for local use (2025-2026)](10-local-llms/_04_popular-model-families-for-local-use-2025-2026.md) · [Tools & runtimes](10-local-llms/_05_tools-and-runtimes.md) · [Hardware requirements (approximate, quantized GGUF)](10-local-llms/_06_hardware-requirements-approximate-quantized-gguf.md) · [Context window and speed considerations](10-local-llms/_07_context-window-and-speed-considerations.md) · [CLI example](10-local-llms/_08_cli-example.md) · [Trade-offs summary](10-local-llms/_09_trade-offs-summary.md) · [Further reading](10-local-llms/_10_further-reading.md)

**[Local Vision Models](11-local-vision-models/)**
[Overview](11-local-vision-models/_01_overview.md) · [Why on-device vision](11-local-vision-models/_02_why-on-device-vision.md) · [Key concepts](11-local-vision-models/_03_key-concepts.md) · [Popular models](11-local-vision-models/_04_popular-models.md) · [Frameworks for local vision inference](11-local-vision-models/_05_frameworks-for-local-vision-inference.md) · [Code example: running YOLOv8n locally with Ultralytics](11-local-vision-models/_06_code-example-running-yolov8n-locally-with-ultralytics.md) · [Typical use cases](11-local-vision-models/_07_typical-use-cases.md) · [Hardware requirements](11-local-vision-models/_08_hardware-requirements.md) · [Trade-offs](11-local-vision-models/_09_trade-offs.md) · [Further reading](11-local-vision-models/_10_further-reading.md)

**[Local Speech Models](12-local-speech-models/)**
[Overview](12-local-speech-models/_01_overview.md) · [Why on-device speech](12-local-speech-models/_02_why-on-device-speech.md) · [Key concepts](12-local-speech-models/_03_key-concepts.md) · [Speech-to-text (ASR)](12-local-speech-models/_04_speech-to-text-asr.md) · [Text-to-speech (TTS)](12-local-speech-models/_05_text-to-speech-tts.md) · [Wake word / keyword spotting](12-local-speech-models/_06_wake-word-keyword-spotting.md) · [Code/CLI example: transcribing audio with whisper.cpp](12-local-speech-models/_07_codecli-example-transcribing-audio-with-whispercpp.md) · [Latency/accuracy trade-offs (Whisper model sizes)](12-local-speech-models/_08_latencyaccuracy-trade-offs-whisper-model-sizes.md) · [Typical use cases](12-local-speech-models/_09_typical-use-cases.md) · [Hardware requirements](12-local-speech-models/_10_hardware-requirements.md) · [Trade-offs](12-local-speech-models/_11_trade-offs.md) · [Further reading](12-local-speech-models/_12_further-reading.md)

**[llama.cpp](16-llama-cpp/)**
[Overview](16-llama-cpp/_01_overview.md) · [Key concepts](16-llama-cpp/_02_key-concepts.md) · [Quantization levels](16-llama-cpp/_03_quantization-levels.md) · [Backends supported](16-llama-cpp/_04_backends-supported.md) · [Building from source](16-llama-cpp/_05_building-from-source.md) · [CLI usage example](16-llama-cpp/_06_cli-usage-example.md) · [llama-server: OpenAI-compatible API mode](16-llama-cpp/_07_llama-server-openai-compatible-api-mode.md) · [Bindings](16-llama-cpp/_08_bindings.md) · [Performance tuning flags](16-llama-cpp/_09_performance-tuning-flags.md) · [Trade-offs](16-llama-cpp/_10_trade-offs.md) · [Further reading](16-llama-cpp/_11_further-reading.md)

**[Ollama](17-ollama/)**
[Overview](17-ollama/_01_overview.md) · [Key concepts](17-ollama/_02_key-concepts.md) · [Model library](17-ollama/_03_model-library.md) · [CLI commands](17-ollama/_04_cli-commands.md) · [Modelfile example](17-ollama/_05_modelfile-example.md) · [REST API](17-ollama/_06_rest-api.md) · [OpenAI-compatible API mode](17-ollama/_07_openai-compatible-api-mode.md) · [GPU support](17-ollama/_08_gpu-support.md) · [Integration with tools](17-ollama/_09_integration-with-tools.md) · [Trade-offs](17-ollama/_10_trade-offs.md) · [Further reading](17-ollama/_11_further-reading.md)


### Frameworks

**[ONNX & ONNX Runtime](13-onnx/)**
[Overview](13-onnx/_01_overview.md) · [Key concepts](13-onnx/_02_key-concepts.md) · [Core workflow: export → optimize → deploy](13-onnx/_03_core-workflow-export-optimize-deploy.md) · [Execution Providers](13-onnx/_04_execution-providers.md) · [Python code example: export PyTorch → ONNX, run with onnxruntime](13-onnx/_05_python-code-example-export-pytorch-onnx-run-with-onnxruntime.md) · [Tooling ecosystem](13-onnx/_06_tooling-ecosystem.md) · [Trade-offs](13-onnx/_07_trade-offs.md) · [Further reading](13-onnx/_08_further-reading.md)

**[TensorFlow Lite / LiteRT](14-tensorflow-lite/)**
[Overview](14-tensorflow-lite/_01_overview.md) · [Key concepts](14-tensorflow-lite/_02_key-concepts.md) · [Core workflow: convert → optimize → deploy](14-tensorflow-lite/_03_core-workflow-convert-optimize-deploy.md) · [Delegates for hardware acceleration](14-tensorflow-lite/_04_delegates-for-hardware-acceleration.md) · [Code examples](14-tensorflow-lite/_05_code-examples.md) · [Tooling ecosystem](14-tensorflow-lite/_06_tooling-ecosystem.md) · [Relationship to TensorFlow Lite for Microcontrollers](14-tensorflow-lite/_07_relationship-to-tensorflow-lite-for-microcontrollers.md) · [LiteRT Next and project direction](14-tensorflow-lite/_08_litert-next-and-project-direction.md) · [Trade-offs](14-tensorflow-lite/_09_trade-offs.md) · [Further reading](14-tensorflow-lite/_10_further-reading.md)

**[Core ML](15-coreml/)**
[Overview](15-coreml/_01_overview.md) · [Key concepts](15-coreml/_02_key-concepts.md) · [Core workflow: convert → optimize → deploy](15-coreml/_03_core-workflow-convert-optimize-deploy.md) · [Compute units and automatic device selection](15-coreml/_04_compute-units-and-automatic-device-selection.md) · [Swift code example: running a model with Vision](15-coreml/_05_swift-code-example-running-a-model-with-vision.md) · [Tooling ecosystem](15-coreml/_06_tooling-ecosystem.md) · [Trade-offs](15-coreml/_07_trade-offs.md) · [Further reading](15-coreml/_08_further-reading.md)

---

Start with **Edge AI Fundamentals** and **On-Device AI** for the core concepts, then
branch into whichever platform or technique is relevant to you. **Edge AI Projects**
has hands-on project ideas that tie the topics together.

## Key references & documentation

The most important official docs, papers, and projects across every topic in this
repo — each topic folder's own `further-reading` file has the full, topic-scoped list.

**Runtimes & frameworks**
[ONNX Runtime](https://onnxruntime.ai) · [TensorFlow Lite / LiteRT](https://ai.google.dev/edge/litert) · [PyTorch ExecuTorch](https://pytorch.org/executorch) · [Core ML / coremltools](https://developer.apple.com/documentation/coreml) · [llama.cpp](https://github.com/ggml-org/llama.cpp) · [Ollama](https://ollama.com) · [MediaPipe Solutions](https://ai.google.dev/edge/mediapipe) · [Hugging Face Transformers.js](https://huggingface.co/docs/transformers.js) · [TensorFlow.js](https://www.tensorflow.org/js) · [WebLLM](https://webllm.mlc.ai) · [Ultralytics YOLO](https://docs.ultralytics.com) · [whisper.cpp](https://github.com/ggml-org/whisper.cpp) · [Hugging Face Optimum](https://huggingface.co/docs/optimum)

**Web platform specs**
[MDN: WebGPU / WebAssembly / Web ML APIs](https://developer.mozilla.org/) · [W3C WebGPU spec](https://gpuweb.github.io/gpuweb/) · [W3C WebNN spec](https://www.w3.org/TR/webnn/) · [WebAssembly.org](https://webassembly.org) · [Bytecode Alliance (Wasmtime/WASI)](https://bytecodealliance.org)

**Mobile platform docs**
[Android ML Kit](https://developers.google.com/ml-kit) · [Android AICore / Gemini Nano](https://developer.android.com/ai/aicore) · [Apple Vision framework](https://developer.apple.com/documentation/vision) · [Apple Create ML](https://developer.apple.com/documentation/createml) · [Apple Foundation Models framework](https://developer.apple.com/documentation/foundationmodels)

**Optimization & compression papers**
[MobileNets (Howard et al.)](https://arxiv.org/abs/1704.04861) · [EfficientNet (Tan & Le)](https://arxiv.org/abs/1905.11946) · [Quantization survey (Gholami et al.)](https://arxiv.org/abs/2103.13630) · [GPTQ (Frantar et al.)](https://arxiv.org/abs/2210.17323) · [AWQ (Lin et al.)](https://arxiv.org/abs/2306.00978) · [QLoRA (Dettmers et al.)](https://arxiv.org/abs/2305.14314) · [Deep Compression (Han et al.)](https://arxiv.org/abs/1510.00149) · [Lottery Ticket Hypothesis (Frankle & Carbin)](https://arxiv.org/abs/1803.03635) · [Knowledge Distillation (Hinton et al.)](https://arxiv.org/abs/1503.02531)

**Architecture & distributed learning**
[FedAvg (McMahan et al.)](https://arxiv.org/abs/1602.05629) · [Federated learning survey (Kairouz et al.)](https://arxiv.org/abs/1912.04977) · [Neurosurgeon: cloud/edge split computing](https://dl.acm.org/doi/10.1145/3037697.3037698) · [AWS IoT Greengrass](https://aws.amazon.com/greengrass/) · [Azure IoT Edge](https://azure.microsoft.com/en-us/products/iot-edge)

**Books**
*TinyML* — Pete Warden & Daniel Situnayake (O'Reilly) · *Efficient Processing of Deep Neural Networks* — Sze, Chen, Yang, Emer

**Tools**
[Netron](https://github.com/lutzroeder/netron) (model visualizer) · [Edge Impulse](https://edgeimpulse.com) · [Microsoft Olive](https://github.com/microsoft/olive)
