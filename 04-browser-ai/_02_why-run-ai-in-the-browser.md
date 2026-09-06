# Browser AI: Running Machine Learning Client-Side — Why run AI in the browser

- **Privacy** — user data (photos, audio, text, webcam frames) never leaves the device. Useful for health, biometric, or sensitive-document use cases.
- **Zero inference cost / no server bill** — compute is donated by the client; no GPU fleet to provision or scale.
- **Latency** — no network round trip; important for real-time video/audio filters, autocomplete, and interactive tools.
- **Offline-capable PWAs** — combined with Service Workers and the Cache API, a model can be cached and the app can run fully offline after first load.
- **Reduced operational surface** — no inference API to secure, rate-limit, or keep online.

Trade-offs: download size (models are multi-MB to multi-GB), device heterogeneity (a low-end phone and a gaming desktop get wildly different throughput), and battery/thermal impact.
