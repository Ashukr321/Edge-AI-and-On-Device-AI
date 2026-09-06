# Model Quantization — Overview

Quantization reduces the numeric precision used to represent a model's weights and/or activations — typically from 32-bit floating point down to 16-bit, 8-bit, or even 4-bit representations. This shrinks model size, cuts memory bandwidth (often the real bottleneck in inference), and lets hardware use faster integer arithmetic units. It's usually the single highest-leverage technique for deploying a model on constrained hardware, from mobile phones to microcontrollers to running large language models on a single consumer GPU.
