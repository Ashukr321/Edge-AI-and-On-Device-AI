# Why Frontend Devs Should Care

- **No backend inference bill.** The model runs on the user's device/GPU, not your server — cost scales with users' hardware, not your cloud spend.
- **Privacy by default.** User data (images, audio, text) never leaves the browser — useful for anything sensitive (health, documents, photos).
- **Works offline.** Once the model is cached (via Service Worker / Cache API / IndexedDB), the feature works with no network.
- **Lower latency for small models.** No round trip to a server — first-token/first-result latency can beat a network call, especially on flaky connections.
- **It's now a "just add a library" problem.** Transformers.js, ONNX Runtime Web, TensorFlow.js, and WebLLM ship pretrained models that load with a few lines of JS — no ML background required to ship a real feature.

The trade-off you're signing up for: bigger initial download (model weights),
device-dependent performance, and no control over the exact hardware it runs
on. See [Trade-offs & Challenges](_09_trade-offs-and-challenges.md).
