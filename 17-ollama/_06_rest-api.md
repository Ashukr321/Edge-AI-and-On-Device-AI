# Ollama — REST API

The daemon exposes a native REST API on `localhost:11434` by default:

```bash
curl http://localhost:11434/api/generate -d '{
  "model": "llama3.1:8b",
  "prompt": "Why is the sky blue?",
  "stream": false
}'
```

```bash
curl http://localhost:11434/api/chat -d '{
  "model": "llama3.1:8b",
  "messages": [{"role": "user", "content": "Summarize TCP handshake in 2 lines."}]
}'
```
