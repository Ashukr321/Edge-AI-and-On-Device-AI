# Local Speech Models — Why on-device speech

- **Privacy**: voice is uniquely sensitive (biometric, often captures bystanders); keeping audio local avoids sending it anywhere.
- **Latency**: wake-word detection must respond in milliseconds; even full ASR benefits from avoiding network round-trips for a responsive assistant feel.
- **Offline reliability**: dictation, meeting transcription, and voice control need to work without connectivity (cars, flights, field work).
- **Continuous listening cost**: an always-on wake-word detector must run at near-zero power draw, which rules out any cloud-based approach for that stage regardless of privacy concerns.
