---
title: "DVLAA launches local security range for LLM and agent training"
slug: "dvlaa-launches-local-security-range-for-llm-and-agent-training"
description: "DVLAA (Damn Vulnerable LLM and Agent Application) is a localized security range platform for testing, educational drills, and defense verification of large language model (LLM) and agent..."
date: 2026-11-18T18:09:03+05:30
tags: [LLMSecurity, AIAgents, CTF, OWASP, Flask, Docker]
categories: ["AI", "AI Security", "Large Language Models", "AI Agents", "DevOps"]
image: "https://avatars.githubusercontent.com/u/88639567?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# DVLAA launches local security range for LLM and agent training

DVLAA (Damn Vulnerable LLM and Agent Application) is a localized security range platform for testing, educational drills, and defense verification of large language model (LLM) and agent applications. The project centers on the OWASP LLM Top 10 and Agent Application Security Top 10 risk frameworks, covering typical scenarios such as prompt injection, sensitive information leakage, RAG poisoning, tool abuse, permission boundaries, memory contamination, output processing, and resource consumption.

## 🔍 Overview
The platform operates as a unified training environment that integrates theoretical vulnerability introductions, interactive answering pages, and state-machine verification. It is designed as a "theory-first" entry structure, where users first review vulnerability definitions, attack surfaces, and risk boundaries before proceeding to interactive challenges. The system builds a complete training loop: from vulnerability introduction to answering, model/state machine interaction, audit panels, flag verification, and write-ups (WP).

## 🧩 How it works
DVLAA uses a Flask console as its main entry point, organizing capabilities into a monolithic Flask application with lightweight sidecar containers. The system validates payloads through real model responses, tool calls, state machines, or multi-turn context progression, rather than relying on hardcoded frontend rules.

*   **LLM Focus**: Emphasizes risks in prompts, context, RAG, output processing, tool calls, and resource consumption.
*   **Agent Focus**: Emphasizes goal hijacking, tool abuse, identity/permissions, supply chain, code execution, memory contamination, multi-agent communication, cascade failures, human-machine trust, and runaway agents.
*   **Question Formats**: Includes chat terminals, business command workspaces, product simulation skins, and read-only material workspaces depending on the track.

## ⚙️ Key details
The platform includes 81 local training questions, structured as follows:

| Question Type | Count | Description |
| :--- | :--- | :--- |
| OWASP LLM Sub-questions | 24 | Derived from the LLM Top 10 framework |
| Agent Scenarios | 10 | Derived from the Agent Security Top 10 framework |
| Comprehensive Attack/Defense | 11 | Integrated scenarios |
| AWDP Attack/Defense Contest | 30 | Contest-based questions |
| Real Contest Adaptations | 6 | LLM poisoning CTFs adapted from real contests |

Key features include:
*   **Source Code & Prompt Viewer**: Users can view system prompts, runtime configurations, and core implementations on question pages; runtime random flags are replaced with placeholders.
*   **Model Management Backend**: Supports configuration for local models, Ollama, SiliconFlow, and OpenAI-Compatible services, with API key masking and connection testing.
*   **AWDP Dual-Track Environment**: Offers a default product simulation track (no official image pull required) and an option to install and start official containers (Dify, RAGFlow, Langflow, Flowise, Open WebUI, n8n) for real reproduction.
*   **Bilingual & Theme Support**: Top navigation allows toggling between dark/light themes and Chinese/English interfaces, with preferences saved locally in the browser.
*   **Learning Resources**: Provides built-in Chinese study materials, Markdown/PDF upload, online reading, and material classification management.

## 🚀 Availability
DVLAA is available for local execution via direct Python running or Docker image deployment to independent containers. All vulnerability environments are exposed through a single gateway port (5080). Runtime data isolation ensures that model configurations, uploaded materials, and downloaded models are stored in runtime directories or Docker data volumes. An online AI security training entry point has been integrated with Prompt Airlines, providing a five-level Chinese question guide, stable WPs, and system-internal transfer for real interaction.

#LLMSecurity #AIAgents #CTF #OWASP #Flask #Docker

---

*Source: [Tcotl/DVLAA](https://github.com/Tcotl/DVLAA)*
