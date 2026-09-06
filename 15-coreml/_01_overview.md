# Core ML — Overview

Core ML is Apple's first-party framework for running machine learning models on-device across iOS, iPadOS, macOS, watchOS, tvOS, and visionOS. It is the deployment target of choice for Apple platforms because it is deeply integrated with the OS: it automatically schedules work across CPU, GPU, and the Apple Neural Engine (ANE), integrates with Xcode for model inspection/profiling, and plugs directly into higher-level frameworks like Vision, Natural Language, and Sound Analysis.

Models are shipped as `.mlmodel` (the older, single-file format) or `.mlpackage` (the current default — a directory bundle that can hold multiple weight representations, metadata, and support files, similar in spirit to how `.app` bundles work). Apps typically don't train models in Core ML directly; they convert a model trained elsewhere (PyTorch, TensorFlow) using **coremltools**, or train a simple model with no code using **Create ML**.
