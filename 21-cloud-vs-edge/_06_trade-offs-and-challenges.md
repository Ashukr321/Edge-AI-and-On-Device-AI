# Cloud vs. Edge vs. Hybrid — Trade-offs & challenges

- Hybrid architectures are more flexible but also more complex to build,
  test, and monitor — you now have two (or more) execution paths to keep
  in sync (feature parity, consistent preprocessing, versioning across
  both sides).
- Edge/on-device deployments shift ongoing engineering cost from cloud
  infra spend toward fleet management, OTA, and device fragmentation
  handling.
- Cloud-only architectures are the fastest to iterate on early in a
  product's life but become expensive and latency-limited as usage
  scales, motivating a later migration to edge/hybrid.
- Moving from cloud-only to edge/hybrid later is nontrivial: it usually
  requires re-optimizing the model for constrained hardware and building
  entirely new deployment/monitoring infrastructure.
