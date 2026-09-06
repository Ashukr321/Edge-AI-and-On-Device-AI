# Cloud vs. Edge vs. Hybrid — Real-world examples

- **Pure cloud**: large general-purpose LLM chat products, where model
  size and knowledge breadth dominate and per-request latency of ~1s is
  acceptable.
- **Pure edge (gateway)**: a factory's on-prem server running defect
  detection across dozens of camera feeds — keeps video data on-site,
  avoids per-frame cloud egress costs, tolerates a single point of
  compute since it's on a maintained industrial PC.
- **Pure on-device**: smartphone keyboard next-word prediction — must
  work offline, needs to respond in single-digit milliseconds per
  keystroke, and typed text is highly sensitive.
- **Hybrid — cloud training + edge inference**: the overwhelmingly common
  pattern — train centrally on aggregated data, deploy the compiled model
  to edge/on-device, periodically retrain and push updates.
- **Hybrid — edge preprocessing + cloud heavy lifting**: a smart doorbell
  camera runs cheap on-device motion/person detection continuously, and
  only uploads a clip to the cloud for a heavier "who is this" recognition
  pass when motion is detected — saves bandwidth and battery versus
  streaming everything.
- **Hybrid — model cascading**: a voice assistant runs wake-word detection
  and simple command parsing fully on-device, but escalates open-ended
  or ambiguous queries to a cloud LLM.
