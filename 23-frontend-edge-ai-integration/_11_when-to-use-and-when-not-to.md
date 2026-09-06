# When to Use It, and When Not To

## Use in-browser/edge AI when...

| Scenario | Why |
|---|---|
| User data is sensitive (photos, documents, health/voice notes) | Data never leaves the device — no upload, no compliance/privacy exposure |
| Feature must work offline or on flaky networks (field apps, kiosks, PWAs) | No round trip; once cached, it runs with zero network |
| High request volume, simple model (spam/toxicity filter, background removal, tagging) | Cost shifts to the user's device instead of your inference bill scaling with traffic |
| Low-latency interactive feedback (live webcam filter, as-you-type classification) | No network round trip; can respond every frame |
| You control the audience's hardware roughly (internal tool, known device tier, desktop-first app) | Predictable performance without a fallback path to maintain |
| Prototyping/demo where you don't want to stand up a backend at all | Ship a static site, done |

## Don't use it when...

| Scenario | Why not |
|---|---|
| You need a large/frontier model (GPT/Claude-class LLM, big diffusion image model) | Too large to download/run in a browser; quality gap vs. cloud is too big for the task |
| Your audience is mostly low-end/older mobile devices | Model won't fit in memory or will run too slowly to be usable — a bad first impression is worse than a network call |
| You must guarantee a consistent latency/accuracy SLA | Performance varies by device/browser; you can't promise a number you don't control |
| Output must be centrally auditable, logged, or rate-limited (compliance, abuse prevention) | Nothing runs on your server, so you have no visibility or control over individual runs |
| You need to patch a model bug quickly across all users | Fixing it means shipping a new frontend deploy, not a backend hotfix |
| Users are extremely sensitive to app size / first-load time (e.g. thin landing pages, ad-funnel pages) | A 20–500MB model download kills conversion-focused pages |
| The task genuinely needs server-side data (a database, another user's data, a paid third-party API) | Edge AI only helps with local inference — it doesn't replace a backend for anything that needs shared state |

## Quick decision rule

Ask: *"Does this feature only need the data already in front of the user, and would a cloud call be overkill for it?"* — if yes, edge AI is a good fit. If the task needs scale, auditability, or a model too big to ship to a browser, keep it server-side (or use the [hybrid pattern](_03_architecture-patterns.md#2-hybrid-edge-first-cloud-fallback): try local, fall back to cloud).
