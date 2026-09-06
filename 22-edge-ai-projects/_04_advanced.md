# Edge AI Projects — Advanced

11. **Run a local LLM in-browser with WebGPU**
    Deploy a small (1–3B parameter) quantized LLM to run entirely
    client-side in the browser using WebLLM (built on Apache TVM) or
    Transformers.js with a WebGPU backend — no server inference call at
    all after the model downloads.
    *Stack: WebLLM or Transformers.js, WebGPU-capable browser.*

12. **On-device LLM assistant on a phone**
    Deploy a quantized small language model (via MLC-LLM, ExecuTorch, or
    llama.cpp's Android/iOS bindings) to run a chat/summarization feature
    fully on a phone, and measure tokens/sec, memory footprint, and
    battery drain across a few device tiers.
    *Stack: MLC-LLM or llama.cpp (Android/iOS build), a phone with an
    NPU (Snapdragon/Apple Silicon).*

13. **Split computing between a wearable and a phone**
    Partition a network so early layers run on a resource-constrained
    wearable (or simulate one on a Raspberry Pi Zero) and later layers run
    on a paired phone, transmitting only the intermediate activation —
    measure the bandwidth/latency/accuracy trade-off versus running the
    whole model on either device alone.
    *Stack: PyTorch/TensorFlow for the split model, BLE/Wi-Fi Direct for
    the link between devices.*

14. **Full MLOps loop for an edge fleet**
    Build the complete loop from `20-edge-ai-architecture`: train a
    model, quantize/compile it, deploy to a simulated fleet of Docker
    containers standing in for devices, collect synthetic telemetry
    (latency, confidence drift), detect drift, retrain, and push a new
    versioned model with staged rollout and rollback.
    *Stack: MLflow for versioning, Docker Compose to simulate the fleet,
    a simple message broker (MQTT) for telemetry.*

15. **Neural architecture search for a target latency budget**
    Use a lightweight NAS or architecture-scaling approach (e.g.
    EfficientNet-style compound scaling, or a hardware-aware search tool)
    to find the best-accuracy architecture that fits a fixed latency
    budget on a specific target device, then validate the predicted vs.
    measured on-device latency.
    *Stack: PyTorch, a NAS library (e.g. Once-for-All or a compound-
    scaling script), the actual target device for latency measurement.*
