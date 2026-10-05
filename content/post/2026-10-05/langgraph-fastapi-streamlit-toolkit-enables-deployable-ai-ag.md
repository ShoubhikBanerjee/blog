---
title: "LangGraph‑FastAPI‑Streamlit Toolkit Enables Deployable AI Agent Services"
slug: "langgraphfastapistreamlit-toolkit-enables-deployable-ai-agent-services"
description: "A new open‑source toolkit delivers a complete stack for running AI agents. It combines a LangGraph agent, a FastAPI service, a Python client, and a Streamlit chat interface, all wired together with..."
date: 2026-10-05T18:05:56+05:30
tags: [LangGraph, FastAPI, Streamlit, AIagents]
categories: ["AI", "Machine Learning", "AI Agents", "Software Engineering", "DevOps"]
image: "https://avatars.githubusercontent.com/u/8251002?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LangGraph‑FastAPI‑Streamlit Toolkit Enables Deployable AI Agent Services

A new open‑source toolkit delivers a complete stack for running AI agents. It combines a LangGraph agent, a FastAPI service, a Python client, and a Streamlit chat interface, all wired together with Pydantic schemas.

## 🔍 Overview
- The repository provides a **LangGraph agent** built on version 1.0 features such as `interrupt()`, `Command`, `Store`, and `langgraph-supervisor`.
- A **FastAPI service** exposes the agent via streaming and non‑streaming endpoints and also via the AG‑UI protocol for front‑ends like CopilotKit.
- A **client library** lets external code call the service.
- A **Streamlit app** offers a user‑friendly chat UI with voice input/output, a "Previous Chats" sidebar, and a star‑based feedback component linked to LangSmith.

## 🧩 How it Works
- **Data models** and runtime settings are defined with **Pydantic** in `src/schema/`.
- The service runs asynchronously (`async/await`) to handle concurrent requests efficiently.
- **Advanced streaming** supports both token‑based and message‑based streams.
- Multiple agents can be hosted simultaneously and addressed by URL path (see `/info` for available agents and models).
- A basic **RAG agent** uses **ChromaDB** for retrieval‑augmented generation.
- **Content moderation** is enforced through the Safeguard module, which requires a Groq API key.
- Chat history for each user‑agent pair is accessible via `/threads` and shown in the Streamlit sidebar.

## ⚙️ Key Features
- Human‑in‑the‑loop support (`interrupt()`).
- Flow control with `Command` objects.
- Long‑term memory via `Store`.
- `langgraph-supervisor` for supervising agent execution.
- Streaming and non‑streaming FastAPI endpoints.
- AG‑UI protocol compatibility.
- Voice interaction in the Streamlit UI.
- Star‑rating feedback integrated with LangSmith.
- Robust unit and integration tests.
- Dockerfiles and a Docker‑Compose setup for rapid development and hot‑reloading.

## 🚀 Availability
- Install the package with **uv** (recommended) or `pip install .`.
- At least one LLM API key is required to run agents.
- The Docker configuration is the simplest way to set up the environment and see immediate code changes reflected in the running services.
- Source structure includes:
  - `src/agents/` – agent implementations
  - `src/schema/` – protocol schemas
  - `src/core/` – LLM definitions and settings
  - `src/service/service.py` – FastAPI service
  - `src/client/client.py` – client library
  - `src/streamlit_app.py` – Streamlit UI
  - `tests/` – test suite

## 💡 Practical Impact
- Developers can prototype, test, and deploy AI agents without building infrastructure from scratch.
- The asynchronous design and Docker support streamline scaling and local iteration.
- Integrated moderation and feedback mechanisms help maintain safe and user‑centric interactions.
- Compatibility with AG‑UI opens the door to a variety of front‑end experiences.


#LangGraph #FastAPI #Streamlit #AIagents

---

*Source: [JoshuaC215/agent-service-toolkit](https://github.com/JoshuaC215/agent-service-toolkit)*
