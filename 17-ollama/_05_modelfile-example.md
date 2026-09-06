# Ollama — Modelfile example

A Modelfile customizes a base model's system prompt, sampling parameters, or template without retraining anything:

```dockerfile
FROM llama3.1:8b

# Lower temperature for more deterministic, focused answers
PARAMETER temperature 0.3
PARAMETER num_ctx 8192

SYSTEM """
You are a terse senior backend engineer. Answer in short,
direct sentences. Prefer code over explanation.
"""
```

Build and run it:

```bash
ollama create terse-engineer -f Modelfile
ollama run terse-engineer "How do I paginate a Postgres query?"
```
