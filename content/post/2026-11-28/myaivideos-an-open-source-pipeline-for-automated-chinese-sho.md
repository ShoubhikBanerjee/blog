---
title: "myAiVideos: An open-source pipeline for automated Chinese short-video production"
slug: "myaivideos-an-open-source-pipeline-for-automated-chinese-short-video-production"
description: "myAiVideos is a new open-source engineering project designed for the automated production of Chinese-language short videos. It covers the full pipeline from topic discovery through creative..."
date: 2026-11-28T18:07:42+05:30
tags: [OpenSource, VideoGeneration, FastAPI, Java, AIModels]
categories: ["AI", "Generative AI", "Open Source Software", "Video Production", "Software Architecture"]
image: "https://avatars.githubusercontent.com/u/94903442?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# myAiVideos: An open-source pipeline for automated Chinese short-video production

myAiVideos is a new open-source engineering project designed for the automated production of Chinese-language short videos. It covers the full pipeline from topic discovery through creative generation, visuals, audio, and post-production, all the way to distribution.

## 🔍 Overview
The system is built as a modular platform that coordinates multiple AI models to handle generation and quality gating. Its architecture is designed to be decoupled, allowing individual layers of the pipeline to be independently replaced.

## 🧩 How it works
The project utilizes a seven-layer pipeline architecture:
- **L1**: Topic
- **L2**: Creative
- **L3**: Visual
- **L4**: Audio
- **L5**: Post-production
- **L6**: Distribution
- **L7**: Optimization

Orchestration is managed by a FastAPI core, while a Java gateway acts as the platform governance layer. The gateway handles authentication, routing, circuit breaking, metering, and observability. Key technical mechanisms include:
- **Multi-model failover**: The Java gateway aggregates DeepSeek, Qwen, and GLM using Resilience4j protection to automatically rotate failed providers.
- **Prompt anchoring**: Maintains the visual identity of subjects across video segments.
- **CLIP gating**: Rejects off-prompt keyframes early using text-image consistency checks.
- **Audio-video sync rescue**: Employs a four-tier strategy involving audio tempo adjustments, video padding, and narration rewrites.

## ⚙️ Key details
The system provides full-stack observability by propagating `trace_id` across Java and Python environments and offering Langfuse call-tree visibility. Metering and rate limiting are handled via an AOP aspect that captures token and cost data without requiring code changes, aggregated by tenant. The production-ready setup includes SSE progress streaming, single-segment regeneration, and rolling log archives.

| Component | Technology / Model |
| :--- | :--- |
| Gateway | Spring Boot 3.5, WebClient, Resilience4j, Caffeine, Prometheus |
| Text LLM | DeepSeek |
| Multimodal Moderation | Zhipu GLM-4V |
| Visuals | Kling v2.5 |
| Speech Synthesis | Volcengine / MiniMax TTS |
| Transcription | faster-whisper |

## 🚀 Availability
myAiVideos is available as an open-source engineering project. It supports local execution using Docker Desktop version 24 or higher. Node.js 20 or higher is required for frontend development, while Python 3.11 or higher is needed for local execution without Docker or for running host tests. Health endpoints are available for the Python API, Java Gateway, and Frontend.

#OpenSource #VideoGeneration #FastAPI #Java #AIModels

---

*Source: [myccarl/ai-shortVideo-pipeline](https://github.com/myccarl/ai-shortVideo-pipeline)*
