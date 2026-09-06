# Edge AI Architecture — Hybrid edge-cloud architectures

Pure edge-only or cloud-only is often wrong; most production systems are
hybrid:

- **Split computing / model partitioning**: split a network at an
  intermediate layer — early layers run on-device (cheap, reduces data
  volume), the intermediate "bottleneck" activation is sent to the cloud,
  and later, heavier layers run there. This trades some transmitted data
  for cloud-scale compute on the wost part of the model.
- **Model cascading (edge → cloud fallback)**: a fast, cheap edge model
  handles the majority of "easy" inputs; only low-confidence or otherwise
  flagged inputs are escalated to a larger cloud model. Common in speech
  recognition (on-device wake word → cloud ASR for full transcription)
  and content moderation.
- **Federated learning**: instead of moving data to a central trainer,
  the model is sent to devices, trained locally on private data, and only
  model updates (gradients/weight deltas) are sent back and aggregated
  (e.g. FedAvg) — used when raw data must never leave the device but the
  global model should still improve.
- **Edge preprocessing + cloud heavy lifting**: the edge does cheap
  filtering (motion detection, voice activity detection, deduplication)
  and only forwards relevant data to a cloud model for the expensive
  analysis.
- **Cloud training + edge inference**: the default and simplest hybrid —
  training entirely in the cloud, inference entirely at the edge, tied
  together by a periodic model-update channel.
