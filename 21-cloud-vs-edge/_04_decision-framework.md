# Cloud vs. Edge vs. Hybrid — Decision framework

Ask, roughly in this order:

1. **Does the feature need to work offline or with unreliable
   connectivity?** If yes, some meaningful capability must run at the
   edge/on-device — cloud-only is disqualified.
2. **What's the latency budget?** Sub-50ms real-time control (robotics,
   AR, safety interlocks) essentially requires edge/on-device. Sub-second
   is workable via cloud if network conditions are good.
3. **Is the data sensitive or regulated?** Health, biometric, or
   otherwise regulated data often pushes toward on-device/edge to avoid
   transmitting or storing it centrally.
4. **How large/capable does the model need to be?** If the task genuinely
   needs a very large model (e.g. complex reasoning, broad open-domain
   knowledge), cloud may be the only option today; if a small specialized
   model suffices, edge/on-device becomes viable.
5. **What's the expected request volume and its cost profile?** High-volume,
   low-value-per-inference workloads (e.g. every keystroke, every video
   frame) are often too expensive to run in the cloud continuously —
   push them to the edge/device and reserve cloud calls for the
   expensive, infrequent cases.
6. **How often does the model need to improve, and how fast?** If you need
   to ship model improvements hourly/daily to all users at once, cloud is
   far simpler; if periodic OTA updates are acceptable, edge/on-device is
   fine.

If the answers are mixed — e.g. low latency needed for the common case but
occasional need for a bigger model — that's a strong signal for a hybrid
architecture (see `20-edge-ai-architecture`).
