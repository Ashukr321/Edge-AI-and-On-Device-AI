# Android Edge AI — Overview

Android provides several layers for on-device ML: high-level task APIs (ML Kit), a general-purpose mobile inference runtime (TensorFlow Lite / LiteRT), a system-level hardware-acceleration abstraction (the Android Neural Networks API, now deprecated in favor of vendor driver APIs), and — on select devices — a system service for running Google's own on-device foundation model (AICore / Gemini Nano). This document covers the Android-specific pieces; framework-agnostic mobile concepts are in `03-mobile-ai`.
