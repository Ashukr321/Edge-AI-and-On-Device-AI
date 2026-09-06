# Edge AI Projects — Trade-offs & challenges when doing these projects

- Device availability is the biggest practical blocker — many of these
  are far more informative on real hardware than in a simulator/emulator,
  since power/thermal/memory behavior doesn't emulate well.
  Emulators and simulators can be used first to iterate on
  correctness before real device testing.
- Cross-compiling and toolchain setup (especially for MCU-class targets)
  is often the most time-consuming part — budget time for it separately
  from the ML work itself.
- Measuring real device metrics (latency, battery, thermal) requires
  care: warm up the device, run enough iterations, and account for
  thermal throttling skewing later measurements.
