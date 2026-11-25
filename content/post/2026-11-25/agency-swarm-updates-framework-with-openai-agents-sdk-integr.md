---
title: "Agency Swarm Updates Framework with OpenAI Agents SDK Integration and 2.0 Beta"
slug: "agency-swarm-updates-framework-with-openai-agents-sdk-integration-and-2-0-beta"
description: "Agency Swarm has updated to a new SDK-based version, including a 2.0 beta release, designed for building, orchestrating, and managing multi-agent applications. The framework leverages and extends the..."
date: 2026-11-25T22:10:10+05:30
tags: [AgencySwarm, OpenAI, AIAgents, Python, MultiAgent]
categories: ["AI", "AI Agents", "Software Development", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/71930995?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agency Swarm Updates Framework with OpenAI Agents SDK Integration and 2.0 Beta

Agency Swarm has updated to a new SDK-based version, including a 2.0 beta release, designed for building, orchestrating, and managing multi-agent applications. The framework leverages and extends the OpenAI Agents SDK to simplify creating AI agencies, continuing the original vision of Arsenii Shatokhin (aka VRSEN) to structure automation around real-world organizational concepts.

## 🔍 Overview

Agency Swarm provides a structured orchestration layer on top of the OpenAI Agents SDK. Built with a production-ready focus, the framework emphasizes reliability and deployment in real-world environments. It targets the OpenAI Agents SDK and the Responses API.

## 🧩 Key Features

- **Customizable Agent Roles**: Define distinct roles such as CEO, Virtual Assistant, or Developer with tailored instructions, tools, and capabilities.
- **Full Prompt Control**: Maintain complete control over each agent's guiding instructions.
- **Type-Safe Tools**: Develop tools using Pydantic models for automatic argument validation compatible with the OpenAI Agents SDK FunctionTool format. Tools can be created using the `@function_tool` decorator, extending `BaseTool`, or importing OpenAPI schemas via `ToolFactory.from_openapi_schema()`.
- **Orchestrated Communication**: Agents communicate using a dedicated `send_message` tool, with interactions controlled by explicit directional `communication_flows` defined on the Agency.
- **State Persistence**: Persist conversation history across database or file storage using `load_threads_callback` and `save_threads_callback`.

## ⚙️ Technical Specifications

- **Python Support**: Python 3.12+
- **Operating Systems**: macOS, Linux, Windows
- **Default Model**: `gpt-6-luna` (served by the Responses API)
- **LiteLLM Router Integrations**: Anthropic (Claude), Google (Gemini), Grok (xAI), Azure OpenAI, and OpenRouter (gateway)

## 🚀 Getting Started and Migration

To install the framework, use `pip install -U agency-swarm`. To try the 2.0 beta, install using `pip install -U --pre agency-swarm`. Projects transitioning from v0.x or upgrading to v2 can consult the respective Migration Guide and v2 migration notes.

Setup requires an `OPENAI_API_KEY` defined in an auto-loaded `.env` file or exported in the shell environment. It is recommended to begin project development using the Agency Starter Template.

#AgencySwarm #OpenAI #AIAgents #Python #MultiAgent

---

*Source: [VRSEN/agency-swarm](https://github.com/VRSEN/agency-swarm)*
