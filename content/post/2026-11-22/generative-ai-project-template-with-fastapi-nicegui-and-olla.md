---
title: "Generative AI Project Template with FastAPI, NiceGUI, and Ollama"
slug: "generative-ai-project-template-with-fastapi-nicegui-and-ollama"
description: "A new generative‑AI project template combines FastAPI, NiceGUI and Ollama for rapid prototyping."
date: 2026-11-22T22:08:30+05:30
tags: [FastAPI, NiceGUI, Ollama, Docker, Python]
categories: ["AI", "Web Development", "Artificial Intelligence", "Python Programming", "Containerization"]
image: "https://avatars.githubusercontent.com/u/32715913?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Generative AI Project Template with FastAPI, NiceGUI, and Ollama

A new generative‑AI project template combines FastAPI, NiceGUI and Ollama for rapid prototyping.

## 🔍 Overview
- FastAPI backend and NiceGUI frontend for chat.
- Local Ollama or cloud models through LiteLLM.
- uv workspace tooling, tests, Docker Compose and GitHub releases.
- Requires Make, Bash, Git and uv.

## 🧩 How it Works
- Clone the repo: `git clone https://github.com/AmineDjeghri/generative-ai-project-template.git`.
- Navigate into it: `cd generative-ai-project-template`.
- Install dev tools: `make install-dev`.
- Copy the example env: `cp .env.example .env`.
- Configure `INFERENCE_*` and `EMBEDDINGS_*` in `.env` for your model provider.
- Start the app: `make run`.
- Open the frontend at <http://localhost:8080> or the backend API docs at <http://localhost:8000/docs>.
- For local Ollama: `make install-ollama` then `make run-with-ollama`.

## ⚙️ Key Details
- `make docker-compose` – Backend, frontend and Ollama in containers; Compose 2.24+.
- `make docker-compose-cuda` – Same stack with GPU access for Ollama; NVIDIA drivers required.
- `make docker-compose-rebuild` – Rebuild containers after source changes.
- `make run-backend` / `make run-frontend` – Start either application separately.
- Python PyTorch extras are optional for model development; Ollama inference runs outside Python.
- `make install-dev` installs Git hooks in a checkout; `make pre-commit-install` reinstalls them.
- `make test-local` runs offline tests.
- Before a PR, configure the integration services and run `make check` – includes live LLM/Ollama/API tests.
- `make help` lists all targets.
- `make deploy-doc-local` previews documentation.
- uv provisions the Python version set by `requires‑python` in `pyproject.toml`.

## 🚀 Availability
- Repository: <https://github.com/AmineDjeghri/generative-ai-project-template>.
- Local frontend: <http://localhost:8080>.
- Backend API docs: <http://localhost:8000/docs>.

#FastAPI #NiceGUI #Ollama #Docker #Python

---

*Source: [AmineDjeghri/generative-ai-project-template](https://github.com/AmineDjeghri/generative-ai-project-template)*
