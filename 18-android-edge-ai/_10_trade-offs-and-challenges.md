# Android Edge AI — Trade-offs & challenges

- NNAPI's deprecation path means apps that leaned on it exclusively need a migration plan toward vendor delegates or LiteRT's newer delegate APIs.
- Extreme device fragmentation makes exhaustive real-device testing impractical; graceful degradation (CPU fallback) is mandatory, not optional.
- Gemini Nano/AICore features are only available on a subset of devices, requiring a designed fallback (cloud API or feature-off) for the rest of the fleet.
- Play Feature Delivery adds packaging/release complexity in exchange for a smaller base install.
