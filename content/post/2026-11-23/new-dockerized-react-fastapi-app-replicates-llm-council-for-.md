---
title: "New Dockerized React/FastAPI app replicates LLM Council for model comparison"
slug: "new-dockerized-react-fastapi-app-replicates-llm-council-for-model-comparison"
description: "A new React/FastAPI application is available for comparing model answers, peer rankings, and a chairman's synthesis, inspired by Andrej Karpathy's LLM Council concept."
date: 2026-11-23T22:18:20+05:30
tags: [OpenRouter, Ollama, Docker, FastAPI, LLMCouncil]
categories: ["AI", "Large Language Models", "Developer Tools", "Software Engineering", "Infrastructure"]
image: "https://avatars.githubusercontent.com/u/4634893?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Dockerized React/FastAPI app replicates LLM Council for model comparison

A new React/FastAPI application is available for comparing model answers, peer rankings, and a chairman's synthesis, inspired by Andrej Karpathy's LLM Council concept.

## 🧩 How it works
The application allows each conversation to select OpenRouter or Ollama, its specific models, system prompts, and an execution mode. It supports persistent conversations, attachments, and streaming with cancellation and partial-result recovery. Execution is handled through bounded and idempotent model runs, with runtime settings controlled by administrators.

## ⚙️ Key details

- **Dependencies:** The project uses a committed `uv.lock` and `frontend/package-lock.json` to ensure reproducible dependencies.
- **TOON statistics:** Token representation comparisons are provided, but these are explicitly not provider billing.
- **Ports:** The backend is published loopback-only at `http://127.0.0.1:8001`, while the frontend is published on port 80.
- **Proxy Limits:** The frontend `nginx.conf` and optional `nginx/nginx.conf` files both set `client_max_body_size` to 25m. A 20 MiB image becomes approximately 26.7 MiB in base64, which can successfully upload but receive a 413 error at the proxy. To support the full API image limit, the setting must be increased to 40m and the proxy layer rebuilt.
- **Resources:** The backend container has a 1 GiB total memory limit in Compose. PDF workers on Linux can each have a 1 GiB virtual-memory ceiling, with two workers per API process.
- **Databases:** Compose does not provision PostgreSQL or MySQL servers. Adding PostgreSQL requires exporting base runtime dependencies with `--extra database` and rebuilding the image. Finance and embeddings extras similarly require explicit image packaging.
- **Environments:** Python 3.10+ is declared by the project, with CI and the backend image using 3.12. Node 20.19+ or 22.12+ is required by the locked Vite release; the frontend image uses Node 22, while CI tests Node 20.
- **Configuration:** In Docker, keeping a specific build-time setting empty utilizes the same-origin nginx proxy. Changing this setting for built assets requires a rebuild.

## 🚀 Availability
Running the application requires a running Docker engine and current Docker Compose v2. The default backend Dockerfile exports base runtime dependencies only.

#OpenRouter #Ollama #Docker #FastAPI #LLMCouncil

---

*Source: [DmitryBMsk/llm-council-plus](https://github.com/DmitryBMsk/llm-council-plus)*
