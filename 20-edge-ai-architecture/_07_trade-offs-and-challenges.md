# Edge AI Architecture — Trade-offs & challenges

- Split computing reduces on-device compute but reintroduces a network
  dependency and privacy exposure for the transmitted activations.
- Federated learning avoids raw data movement but adds communication
  rounds, non-IID data challenges, and needs care (secure aggregation,
  differential privacy) to avoid leaking information through gradients.
- Staged rollouts and rollback infrastructure are extra engineering work
  that's easy to skip early on and expensive to retrofit later.
- Telemetry from the field is inherently privacy-sensitive; teams must
  balance observability needs against data minimization principles.
