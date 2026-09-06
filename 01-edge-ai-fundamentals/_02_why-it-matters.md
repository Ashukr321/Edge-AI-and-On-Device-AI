# Edge AI Fundamentals — Why it matters

- **Latency**: Round-tripping to the cloud adds tens to hundreds of
  milliseconds of network latency plus queueing/serialization overhead.
  Real-time control loops (robotics, ADAS, industrial safety interlocks)
  cannot tolerate this.
- **Privacy & compliance**: Keeping raw video, audio, or health data local
  avoids transmitting sensitive data off-premises, which simplifies GDPR/
  HIPAA compliance and reduces breach exposure.
- **Bandwidth & cost**: A single 4K camera stream is several Mbps; fleets of
  cameras or sensors uploading raw data continuously would be prohibitively
  expensive and often infeasible over cellular/satellite links. Edge
  inference lets you transmit only summarized events ("person detected",
  "vibration anomaly at 14:32") instead of raw streams.
- **Reliability & offline operation**: Edge/on-device systems keep working
  during network outages — important for factories, vehicles, ships, and
  remote sites.
- **Regulatory data residency**: Some jurisdictions require certain data
  never leave a facility or country.
