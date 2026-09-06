# Mobile AI — Trade-offs & challenges

- **Accuracy vs. size**: aggressive quantization/pruning to fit app-size and latency budgets trades off model accuracy; the right point depends on the feature's tolerance for errors.
- **Fragmentation cost**: supporting the full Android hardware matrix means testing (or at least tolerating graceful fallback) across many delegate/driver combinations.
- **Model updates outside app releases**: dynamic delivery adds infrastructure (hosting, versioning, integrity verification) but decouples model iteration from app-store review cycles.
- **Privacy vs. capability**: on-device keeps data local but caps model capability versus a cloud model; many production features are hybrid for this reason.
- **Testing on-device behavior**: emulators/simulators often don't expose the same NPU/GPU delegates as real hardware, so final validation must happen on physical devices.
