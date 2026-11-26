---
title: "New DSH Plugin Delivers Free Access to Frontier Models Without Login or API Keys"
slug: "new-dsh-plugin-delivers-free-access-to-frontier-models-without-login-or-api-keys"
description: "The plugin installs directly into dsh and activates a free lane to frontier models. Users can access DeepSeek V4.1 Flash, Kimi K3, and other models instantly without creating accounts or managing API..."
date: 2026-11-26T18:08:23+05:30
tags: [AI, OpenAPI, Plugins, FreeModels, DSH, LLM]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Software Development", "API Integration"]
image: "https://avatars.githubusercontent.com/u/245557608?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New DSH Plugin Delivers Free Access to Frontier Models Without Login or API Keys

## 🔍 Overview

The plugin installs directly into dsh and activates a free lane to frontier models. Users can access DeepSeek V4.1 Flash, Kimi K3, and other models instantly without creating accounts or managing API keys. The service is completely free with no usage limits.

## 🧩 How it works

The plugin integrates as a pure mount point requiring no kernel modifications, build steps, or dependencies. It pulls model lists directly from upstream sources and removes unavailable models from the selector based on gateway responses. The plugin handles routing and provides an OpenAI-compatible local forwarding port for integration with other tools.

## ⚙️ Key details

### Available Channels

| Channel | Source | Features |
|---------|--------|----------|
| Free lane | OpenCode Zen gateway | DeepSeek V4.1 Flash, Kimi K3, no authentication |
| Kilo channel | Kilo AI public gateway | Free models, no account or key required |
| Aggregated channel | 77 provider registries | NVIDIA NIM, OpenRouter, Groq, Cerebras, SambaNova, Gemini, DeepSeek, Mistral, Together, Fireworks, SiliconFlow, Nebius, Chutes, Hugging Face, Cloudflare, Z.ai, Kimi, MiniMax, QwenCloud, Bedrock, Vertex, Vercel AI Gateway, Azure OpenAI, FleetRelay, Ollama, LM Studio, llama.cpp |

### Account-based Integrations

Ten account channels are pre-enabled: LobsterAI, Qoder (Chinese version), TRAE, Cline, Loomy, Raccoon, MiniMax Code, ZCode, Gemini, and EAC channel from project maintainers.

### Additional Features

- **Reasoning control**: Models like DeepSeek V4.1 Flash and GLM 5.3 Flash expose reasoning level menus (Off/Low/High/Max)
- **Local dashboard**: Tracks token usage, speed, and latency with in-device analytics
- **Hot reload**: Updates apply immediately without restart
- **Automatic updates**: Built-in checker with rollback capability

## 🚀 Availability

The plugin achieved GitHub Trending #1 and JavaScript weekly trend #1 status. Users can join the OFM technology exchange QQ group (974582805) for support.

#AI #OpenAPI #Plugins #FreeModels #DSH #LLM

---

*Source: [Ebony-Vinyl/dsh-our-free-model](https://github.com/Ebony-Vinyl/dsh-our-free-model)*
