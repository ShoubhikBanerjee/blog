---
title: "PenShot multi-agent system converts scripts to video generation prompts"
slug: "penshot-multi-agent-system-converts-scripts-to-video-generation-prompts"
description: "A new open-source system called PenShot uses a multi-agent LangGraph pipeline to parse scripts of any format and generate coherent, model-ready prompts for text-to-video models including Sora, Veo,..."
date: 2026-11-20T18:09:02+05:30
tags: [AIagents, LangGraph, TextToVideo, ScriptToVideo, MultiAgent, OpenSource]
categories: ["AI", "AI Agents", "Generative AI", "Computer Vision", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/32693265?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# PenShot multi-agent system converts scripts to video generation prompts

A new open-source system called PenShot uses a multi-agent LangGraph pipeline to parse scripts of any format and generate coherent, model-ready prompts for text-to-video models including Sora, Veo, Runway, Kling, and SVD.

## 🔍 Overview
PenShot (剧本分镜智能体) is a script-to-storyboard agent that takes input from movies, anime, short dramas, or novels and produces shot-level descriptions and video generation prompts. It is built on LLMs orchestrated through LangGraph and LlamaIndex, with a focus on maintaining character, scene, and plot consistency across segments.

## 🧩 How it works
The system operates as a directed multi-agent graph:
- **Script parsing agent** → **Storyboard generation agent**
- **Storyboard generation agent** → **Video segmentation agent**
- **Video segmentation agent** → **Prompt conversion agent**
- **Prompt conversion agent** → **Quality audit agent**
- **Quality audit agent** → **Continuity guard agent**
- **Continuity guard agent** → **Auxiliary generation agent** (three-view/background/keyframe)
- **Multi-model adapter** → **Sora / Veo / Runway / 可灵 / SVD**
- **Sora / Veo / Runway / 可灵 / SVD** → **FFmpeg synthesis**
- **FFmpeg synthesis** → **Final film**

Continuity is enforced through a three-view design, a RAG knowledge base, three-tier memory (short/medium/long term), Chroma vector retrieval, snapshot mechanism, and multi-dimensional recall. A task-pool priority queue manages execution order.

## ⚙️ Key details

### Supported input and output
- Accepts arbitrary-format scripts: movies, short dramas, anime, novels
- Auto-identifies scenes, dialogue, and action instructions
- Understands story structure and supports long-text segmented processing
- Outputs shot-granularity segments with precise duration planning adapted to each video model's length limits

### Prompt generation
- Bilingual (Chinese/English) visual descriptions
- Negative prompts
- Audio prompts
- Ready-to-use for Sora, Veo, Runway, Kling (可灵), SVD

### Model and LLM compatibility
| Component | Options |
|---|---|
| Text-to-video models | Sora, Veo, Runway, 可灵, SVD |
| LLM providers | OpenAI, Qwen, DeepSeek, Ollama (pluggable) |

### Integration interfaces
- Python SDK
- REST API
- LangGraph nodes
- Function Calling
- MCP (Model Context Protocol) standard interface
- A2A collaboration protocol

### Reliability features
- Automatic retry and error fallback
- Bidirectional traceability: every storyboard segment links back to its source script position

## 🚀 Availability
- **Package install**: `pip install penshot` (3 lines of code to integrate)
- **Docker**: `docker pull neotems/penshot` to run as a service
- Claimed 5-minute onboarding

## 💡 Why it matters
PenShot addresses the gap between narrative scripts and the strict prompt requirements of current text-to-video models. By combining multi-agent orchestration, persistent memory, vector retrieval, and multi-model adapter layers, it provides an end-to-end pipeline that preserves narrative continuity while outputting prompts tailored to each target video generator.

#AIagents #LangGraph #TextToVideo #ScriptToVideo #MultiAgent #OpenSource

---

*Source: [neopen/story-shot-agent](https://github.com/neopen/story-shot-agent)*
