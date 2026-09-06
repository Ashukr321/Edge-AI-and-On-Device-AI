# Edge AI Architecture — MLOps for edge

Edge MLOps differs from cloud MLOps mainly because you cannot assume
instant, reliable connectivity to the inference host, and you're managing
potentially millions of independent, heterogeneous nodes instead of a
uniform server fleet.

- **Model versioning**: every deployed model artifact needs an immutable
  version id, a manifest describing input/output tensors and
  preprocessing, and compatibility metadata (min OS version, required
  accelerator).
- **Staged rollout / canarying**: roll a new model to 1% of devices,
  watch health signals, then ramp — the on-device analogue of a canary
  deployment.
- **A/B testing on-device**: ship two model variants behind a feature
  flag / experiment id, compare business or quality metrics between
  cohorts before fully rolling out.
- **Rollback**: devices should be able to revert to the last-known-good
  model if the new one causes crashes, latency regressions, or clearly
  wrong predictions, ideally without needing a full app update.
- **Telemetry**: latency percentiles, memory/battery impact, error rates,
  and (privacy-preserving, often aggregated/differentially-private)
  signals about prediction quality.
- **Drift detection**: since you often can't get ground-truth labels from
  the field in real time, teams rely on proxies — input distribution
  shift, confidence score distributions, disagreement with a heavier
  "shadow" model run periodically.
- **Shadow deployment**: run a new model alongside the current production
  model on real device traffic without acting on its output, purely to
  compare predictions before promoting it.
