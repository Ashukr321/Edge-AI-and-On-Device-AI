# Cloud vs. Edge vs. Hybrid — Direct comparison

| Dimension | Cloud | Edge (gateway/on-prem) | On-device |
|---|---|---|---|
| Latency | 50–500+ ms (network + queueing) | 1–50 ms (local network) | <1–20 ms (no network) |
| Connectivity requirement | Always-on required | Local network required | None |
| Compute budget | Effectively unlimited (scale-out GPUs/TPUs) | Bounded by installed hardware (one box) | Very constrained (shared with OS/other apps, power-limited) |
| Model size | Large (billions of params feasible) | Medium (100M–few B params, depends on box) | Small (typically <1–8B, often <100M for real-time) |
| Cost model | Pay-per-inference/opex, scales with usage | Upfront hardware capex + maintenance | Amortized into device BOM cost, ~zero marginal cost |
| Privacy/data residency | Data leaves premises | Data can stay on-site | Data never leaves the device |
| Update cadence | Instant, server-side, no client rollout needed | Requires deployment to the box | Requires OTA push to fleet, staged rollout needed |
| Fleet scale | One logical service | Tens–thousands of boxes | Millions of heterogeneous devices |
| Offline operation | Not possible | Possible if network drops (local processing continues) | Always possible |
| Observability/debugging | Easy (your own servers, full logs) | Moderate (limited number of boxes, can SSH in) | Hard (no direct access, privacy-constrained telemetry) |
