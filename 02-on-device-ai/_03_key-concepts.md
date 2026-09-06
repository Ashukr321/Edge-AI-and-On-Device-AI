# On-Device AI — Key concepts

- **On-device vs. edge vs. cloud inference**: on-device = runs on the
  user's own device; edge = runs on nearby infrastructure (gateway, edge
  server, base station) the user doesn't own; cloud = runs in a remote
  data center. The same model artifact might be deployable to more than
  one tier, but on-device deployment has the tightest constraints.
- **Hybrid/fallback patterns**: many products run a small model on-device
  for common cases and fall back to the cloud for harder queries (model
  cascading), or do on-device preprocessing (e.g. voice activity
  detection) before sending anything to the cloud.
- **Personalization without central data**: on-device learning /
  federated learning lets a model adapt to a user's patterns (e.g.
  keyboard autocorrect) without uploading their raw data.
