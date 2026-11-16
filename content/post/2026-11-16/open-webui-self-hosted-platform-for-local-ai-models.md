---
title: "Open WebUI: Self-Hosted Platform for Local AI Models"
slug: "open-webui-self-hosted-platform-for-local-ai-models"
description: "Open WebUI is a home for AI: an extensible, easy-to-use, self-hosted platform built to run entirely offline. It connects local models through Ollama or uses OpenAI-compatible APIs for local and cloud..."
date: 2026-11-16T22:14:27+05:30
tags: [O, p, e, n, W, e, b, U, I, S, e, l, f, H, o, s, t, e, d, A, I, D, o, c, k, e, r, O, l, l, a, m, a]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "A", "I", "I", "n", "f", "r", "a", "s", "t", "r", "u", "c", "t", "u", "r", "e", ",", "O", "p", "e", "n", "S", "o", "u", "r", "c", "e", ",", "D", "o", "c", "k", "e", "r"]
image: "https://avatars.githubusercontent.com/u/158137808?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Open WebUI: Self-Hosted Platform for Local AI Models

Open WebUI is a home for AI: an extensible, easy-to-use, self-hosted platform built to run entirely offline. It connects local models through Ollama or uses OpenAI-compatible APIs for local and cloud models.

## 🔍 Overview

Supported languages include English, Simplified Chinese, Traditional Chinese, Korean, German, Spanish, French, Italian, Danish, Japanese, Polish, Russian, Bosnian, Arabic, Norwegian, Portuguese (Brazil), Thai, Turkish, Ukrainian, Bengali, Greek, and Vietnamese. A native desktop app is available for macOS, Windows, and Linux.

## 🚀 Installation

**Python Installation**
Run `DATA_DIR=~/.open-webui uvx --python 3.12 open-webui@latest serve`. The web interface is available at `http://localhost:8080`.

**Pip Installation**
Run `pip install open-webui` followed by `open-webui serve`.

**Docker Installation**
Run `docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main`. The web interface is available at `http://localhost:3000`.

## 🐳 Docker Image Variants

| Image Tag | Description |
| :--- | :--- |
| `:main` | Standard image with local AI dependencies |
| `:slim` | Lightweight image using external services for embeddings, document extraction, and voice |
| `:cuda` | Open WebUI with CUDA acceleration |
| `:ollama` | Open WebUI bundled with Ollama |
| `:dev` | Latest development build |

## ⚙️ Configuration & Features

**Environment Variables**
*   `OLLAMA_BASE_URL=http://your-ollama-server:11434` connects to Ollama on another server.
*   `OPENAI_API_KEY=your_secret_key` sets the OpenAI API key.
*   `HF_HUB_OFFLINE=1` disables Hugging Face model downloads for offline use.

**GPU Support**
Use the `--gpus all` option for Nvidia GPU access with the `:cuda` or `:ollama` images. This requires the Nvidia Container Toolkit.

**GitHub Information**
The repository displays stars, forks, watchers, repo size, language count, top language, and last commit date. Social badges link to Discord and GitHub sponsors.

## 📚 Documentation & Support

*   Documentation: https://docs.openwebui.com/
*   Roadmap: https://docs.openwebui.com/roadmap/
*   Installation Docs: https://docs.openwebui.com/getting-started/
*   Troubleshooting: https://docs.openwebui.com/troubleshooting/
*   Updating Guide: https://docs.openwebui.com/getting-started/updating
*   Support: Available via GitHub issues or discussions.

#O #p #e #n #W #e #b #U #I #, # #S #e #l #f #H #o #s #t #e #d #, # #A #I #, # #D #o #c #k #e #r #, # #O #l #l #a #m #a

---

*Source: [open-webui/open-webui](https://github.com/open-webui/open-webui)*
