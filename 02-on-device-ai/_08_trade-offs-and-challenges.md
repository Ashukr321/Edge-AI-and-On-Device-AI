# On-Device AI — Trade-offs & challenges

- Smaller on-device models generally trade some accuracy/capability for
  latency, privacy, and offline availability compared to large cloud
  models.
- Debugging is harder: you can't easily attach a profiler to millions of
  heterogeneous consumer devices the way you can to your own cloud
  fleet — telemetry and crash reporting have to be designed in from the
  start.
- Cross-platform consistency: the same feature often needs a Core ML
  build for iOS and a TFLite/NNAPI build for Android, doubling
  optimization and QA effort.
- Security: on-device model weights can potentially be extracted from an
  app package; sensitive proprietary models need obfuscation/encryption
  strategies.
