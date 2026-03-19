# letta-docker-compse

A project to run letta in docker locally with a local running postgres database and ollama qwen2.5:7b open source model.

## Start

```bash
docker compose up -d

```
You will find 2 servers running

letta server is running at: http://localhost:8283

ollama server is running at: http://127.0.0.1:11434

where you can list the available models: http://127.0.0.1:11434/api/tags


