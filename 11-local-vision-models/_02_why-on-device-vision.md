# Local Vision Models — Why on-device vision

- **Real-time constraints**: camera apps, AR, and robotics need frame-rate inference (often 15-60 FPS) that a network round-trip can't reliably deliver.
- **Privacy**: images/video (faces, documents, home interiors) never leave the device.
- **Offline operation**: document scanners, industrial inspection, and drone/robot vision often run without connectivity.
- **Power/cost**: dedicated NPUs (Apple Neural Engine, Qualcomm Hexagon, Google Edge TPU) run small vision models at a fraction of the power of sending frames to a server.
