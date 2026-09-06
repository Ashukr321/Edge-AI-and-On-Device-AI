# Edge AI Fundamentals — Overview

Edge AI refers to running machine learning inference (and sometimes training)
physically close to where data is generated — on a factory sensor, a
security camera, a car, a retail kiosk, a phone, or a microcontroller —
instead of shipping raw data to a centralized cloud data center for
processing. The "edge" is a spectrum, not a single tier:

```
Sensor/Device  →  Gateway/Edge Server  →  Regional Edge (CDN/telco)  →  Cloud
 (mW-W power)      (W-100s W)              (kW, on-prem racks)          (data center)
```

On-device AI (see `02-on-device-ai`) is the extreme end of this spectrum:
inference that runs entirely on the end-user's device with no network
dependency at all. Edge AI is the broader category that also includes
local gateways, on-premise servers, and industrial edge boxes.
