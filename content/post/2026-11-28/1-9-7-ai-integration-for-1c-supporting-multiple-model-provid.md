---
title: "ИИкона 1.9.7: AI integration for 1C supporting multiple model providers"
slug: "1-9-7-ai-integration-for-1c-supporting-multiple-model-providers"
description: "ИИкона, an extension for working with language models directly within 1C, has released version 1.9.7. This update provides a common connector that enables features such as expert chats, database..."
date: 2026-11-28T22:07:57+05:30
tags: [1C, AI, LLM, Integration, DeveloperTools]
categories: ["AI", "Enterprise Software", "Artificial Intelligence", "Developer Tools", "Integration"]
image: "https://avatars.githubusercontent.com/u/5669019?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ИИкона 1.9.7: AI integration for 1C supporting multiple model providers

ИИкона, an extension for working with language models directly within 1C, has released version 1.9.7. This update provides a common connector that enables features such as expert chats, database access tools, knowledge search, AI-annotated error monitoring, and diagram generation. The release has been verified on 1C:Enterprise 8.3.27.1989 and BSP 3.1.11.466.

## 🧩 How it works

The extension operates through a unified connector that interfaces with various AI models. Availability of tools and attachments depends on the specific model and its API.

*   **Model Support:** Supports OpenAI-compatible APIs, Anthropic, Google Gemini, YandexGPT, and GigaChat.
*   **Additional Providers:** Via compatible APIs, users can connect to OpenRouter, DeepSeek, Mistral, and Qwen. Local models can be accessed through Ollama and LM Studio.
*   **Subscriptions:** A separate adapter is provided for personal subscription-based connections.

## ⚙️ Key details

*   **Vector Search:** Qdrant is connected for vector search capabilities.
*   **Diagram Rendering:** Kroki and Mermaid are used for rendering diagrams.
*   **Name Recognition:** A specific service is connected for name recognition tasks.
*   **Security:** API keys are stored in the protected storage of BSP (БСП).
*   **Developer Access:** Developers can invoke the common connector from their own code.

## 🚀 Availability and Setup

The release is distributed as a `.cfe` file. Installation involves connecting the file via “Administration → Configuration Extensions” and updating the database. Users configure pre-set models in “AIkonna → Administration → AI Models” and verify connections in the model cards. After setting up an expert with a system prompt, users can interact via the “Expert Chat” interface, using `Ctrl+Enter` to send messages and attaching files via the button next to the question input.

## 💡 Why it matters

Version 1.9.7 passed 1,178 primary tests via EDT, 105 role-based executions, and compilation checks. The Sonar Quality Gate status is OK with zero open remarks. The release acknowledges Sergey Boyko for regular testing on “Trade Management,” detailed logs, reproducible scenarios, and suggestions regarding multi-database work, metadata retrieval, agent loop limits, and cost estimation.

#1C #AI #LLM #Integration #DeveloperTools

---

*Source: [andromanpro/1c-ai-connector](https://github.com/andromanpro/1c-ai-connector)*
