# TinyML — Target hardware

| Board / MCU | Core | Notes |
|---|---|---|
| Arduino Nano 33 BLE Sense | Cortex-M4F (nRF52840) | Onboard IMU, mic, gesture/proximity sensors; the reference board for the *TinyML* book and Harvard's tinyML course |
| ESP32 / ESP32-S3 | Xtensa LX6/LX7 | Wi-Fi + BLE onboard, popular for Edge Impulse projects, ESP-NN kernel library |
| STM32 (F4/F7/H7 series) | Cortex-M4/M7 | Wide industrial adoption, supported by STM32Cube.AI (X-CUBE-AI) |
| Cortex-M0+/M3 general | Cortex-M0+/M3 | No FPU on M0/M0+; int8-only inference is the norm |
| Raspberry Pi Pico | Cortex-M0+ (RP2040) | 264 KB RAM, common low-cost TinyML target |
