# Ollama — CLI commands

```bash
ollama pull llama3.1:8b        # download a model
ollama run llama3.1:8b         # run interactively (pulls first if not present)
ollama list                    # show locally downloaded models
ollama ps                      # show models currently loaded in memory
ollama show llama3.1:8b        # show model details (params, template, license)
ollama rm llama3.1:8b          # delete a local model
ollama cp llama3.1:8b my-model # duplicate/rename a model
ollama create my-model -f Modelfile  # build a custom model from a Modelfile
ollama stop llama3.1:8b        # unload a running model from memory
```
