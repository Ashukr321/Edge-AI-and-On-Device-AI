# Ollama — OpenAI-compatible API mode

Ollama also exposes an OpenAI-compatible endpoint, letting existing OpenAI SDK code point at it with only a base-URL change:

```bash
curl http://localhost:11434/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "llama3.1:8b",
    "messages": [{"role": "user", "content": "Give me a haiku about caches."}]
  }'
```

```python
from openai import OpenAI

client = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")  # key unused, but required by the SDK
response = client.chat.completions.create(
    model="llama3.1:8b",
    messages=[{"role": "user", "content": "Give me a haiku about caches."}],
)
print(response.choices[0].message.content)
```
