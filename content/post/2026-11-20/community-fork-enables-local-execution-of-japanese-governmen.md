---
title: "Community fork enables local execution of Japanese Government AI GenAI"
slug: "community-fork-enables-local-execution-of-japanese-government-ai-genai"
description: "A community-driven project has forked the Japanese Digital Agency's open-source Government AI 'GenAI' (Genai) to enable full local operation using local Large Language Models (LLMs) with an..."
date: 2026-11-20T18:09:02+05:30
tags: [OpenSource, LocalAI, JapanGov, LLM, Docker, RAG]
categories: ["AI", "Machine Learning", "Open Source Software", "DevOps", "Government Technology"]
image: "https://avatars.githubusercontent.com/u/5422947?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Community fork enables local execution of Japanese Government AI GenAI

A community-driven project has forked the Japanese Digital Agency's open-source Government AI "GenAI" (Genai) to enable full local operation using local Large Language Models (LLMs) with an OpenAI-compatible API. This unofficial fork addresses the original system's dependency on cloud infrastructure (AWS, Azure, Google Cloud) by replacing those dependencies with local or open-source alternatives, allowing the software to run in closed network environments such as LGWAN.

## 🧩 How it works
The project modifies the Digital Agency's `genai-web` repository (MIT License) to function in a local environment. To facilitate merging with upstream changes, the majority of modifications are concentrated in the OpenGENAI layer (`backend/` and external apps), while the `genai-web` UI is kept largely unmodified to preserve the original user experience. The original `genai-ai-api` is not included in the fork; users must obtain it separately from the Digital Agency's repository if needed.

## ⚙️ Key details
The fork currently stands at version v0.13.0. Key technical and functional features include:
*   **Hardware Flexibility:** Compatible with macOS (Apple Silicon) and Linux systems with NVIDIA GPUs (e.g., NVIDIA DGX Spark).
*   **Security & Deployment:** Production builds use `docker-compose.prod.yml` with TLS termination on port 443. Closed-network verification uses `docker-compose.verify.yml` with HTTP on port 80.
*   **Storage:** Uses SeaweedFS (port 8333), which is not exposed to the host in production. Artifact downloads are handled via a reverse proxy through `S3_PUBLIC_ENDPOINT`.
*   **Core Capabilities:** Includes structured RAG, MCP integration, OCR, skills, Web SSH, and PII detection.

## 📋 Version History
| Version | Key Developments |
| :--- | :--- |
| v0.13.0 | Training, procedure document/audit, and scheduling wizard |
| v0.12.0 | Two-week work, draw.io editing, image generation chat, and per-building model control |
| v0.11.0 | Multi-tenancy, recommended apps, and Markdown editor HTML/PPTX export |
| v0.10.0 | Notebook features (research/organization), Web SSH, and app display editing |
| v0.9.0 | Third implementation wave: Markdown editor and document creation with pluggable generation APIs |
| v0.8.0 | Second implementation wave: Online forms, procedure bundles, application reception, and MCP |
| v0.7.0 | First implementation wave: Document reading/checking, scheduling, and Excel generation |
| v0.6.0 | PII detection, knowledge base pages, large attachment mapreduce, and Dify error classification |
| v0.5.0 | Production static build deployment, multi-model swapping, and SAML authentication hardening |
| v0.4.0 | Structured RAG, knowledge MCP, Dify integration examples, and My Number checking |

## 💡 Why it matters
The project is explicitly an unofficial fork with no relationship to or approval from the Digital Agency. While early releases focused on replacing cloud dependencies with local/OSS components, the project's philosophy has expanded to support actual municipal usage in closed networks. This allows local governments and organizations to utilize GenAI capabilities for administrative tasks (such as document processing and scheduling) without relying on external cloud services.

#OpenSource #LocalAI #JapanGov #LLM #Docker #RAG

---

*Source: [hirokawaguchi/open-genai](https://github.com/hirokawaguchi/open-genai)*
