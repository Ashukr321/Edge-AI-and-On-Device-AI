# Example Live Websites/Demos Built on Edge AI

Real, working sites you can open right now to see in-browser edge AI running
— useful both as inspiration and as a sanity check for what's actually
possible with today's libraries.

| Site | What it demonstrates | Built with |
|---|---|---|
| [huggingface.co/spaces/webml-community](https://huggingface.co/spaces/webml-community) | A collection of dozens of small live demos — background removal, object detection, speech recognition, image captioning, all running client-side | Transformers.js |
| [webllm.mlc.ai](https://webllm.mlc.ai/#chat-demo) | Full chat with an LLM (Llama/Phi/Qwen/Gemma) running entirely in the browser tab, no server calls after model load | WebLLM + WebGPU |
| [huggingface.co/spaces/Xenova/webgpu-video-background-removal](https://huggingface.co/spaces/Xenova/webgpu-video-background-removal) | Real-time video background removal on live webcam feed | Transformers.js + WebGPU |
| [huggingface.co/spaces/Xenova/whisper-web](https://huggingface.co/spaces/Xenova/whisper-web) | Record or upload audio, transcribe fully offline in the browser | Transformers.js (Whisper) |
| [mediapipe-studio (Google)](https://mediapipe-studio.webapps.google.com/studio/demo/object_detector) | Face/hand/pose landmark tracking, object detection, gesture recognition — live webcam demos for every MediaPipe task | MediaPipe Tasks for Web |
| [teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com/) | Train a tiny image/pose/audio classifier in the browser and export it to run in your own web app | TensorFlow.js |
| [tensorflow.org/js/demos](https://www.tensorflow.org/js/demos) | Official gallery: pose detection, pacman-by-webcam, image classification, more | TensorFlow.js |
| [remove.bg](https://www.remove.bg/) (their browser-based quick preview) | Commercial example of instant client-side-feeling background removal before a paid server-side high-res render — a real hybrid pattern | Proprietary, similar architecture |
| [transformers.js demos on GitHub Pages](https://xenova.github.io/transformers.js/) | The library's own interactive playground — try any supported task against any browser-ready model | Transformers.js |

## Why look at these before building

Opening these first tells you, in under a minute, what "good" feels like:
model-load time, whether there's a progress indicator, how it behaves on a
slow connection, and whether it falls back gracefully when WebGPU isn't
available. Copy the parts that feel instant, skip the parts that stall the
UI — most of these are open-source, so the implementation is one click away
(each Hugging Face Space has a "Files" tab with the actual source).
