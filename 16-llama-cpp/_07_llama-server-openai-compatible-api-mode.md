# llama.cpp — llama-server: OpenAI-compatible API mode

`llama-server` runs the model as a persistent local HTTP server exposing an OpenAI-compatible `/v1/chat/completions` endpoint, plus a built-in web chat UI:

```bash
./build/bin/llama-server -m model-Q4_K_M.gguf -c 8192 -ngl 33 --port 8080
```

```bash
curl http://localhost:8080/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "local",
    "messages": [{"role": "user", "content": "Give me a haiku about caches."}]
  }'
```

This makes llama.cpp a drop-in backend for any tool or SDK already written against the OpenAI API shape, just by pointing the base URL at `localhost:8080/v1`.
