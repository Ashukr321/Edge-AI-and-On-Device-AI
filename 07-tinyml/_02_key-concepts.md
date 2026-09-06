# TinyML — Key concepts

- **No dynamic memory allocation.** Embedded runtimes avoid `malloc`/`free` at inference time to prevent heap fragmentation and non-deterministic latency. Memory for tensors is planned and allocated statically (an "arena") ahead of time.
- **No OS, or a minimal RTOS.** Code often runs bare-metal or under a lightweight RTOS (Zephyr, FreeRTOS, Mbed OS). There's no filesystem, no dynamic linker, and often no floating-point hardware unit (FPU).
- **Fixed-point / integer arithmetic.** Many Cortex-M0/M3 cores lack an FPU, so int8 (or int16) fixed-point math is both faster and more power-efficient than float32.
- **Model size ceiling.** Practical TinyML models range from a few KB (simple keyword spotters) to ~1 MB (small vision/audio models). This is a hard constraint, not a preference — the model plus the runtime plus buffers must fit in flash and RAM simultaneously.
- **Deterministic, real-time inference.** Many TinyML applications (anomaly detection, wake-word) run continuously on a duty cycle, so inference latency and power draw per inference matter as much as accuracy.
