---
title: "ViMax v1.2.0 adds Web UI and new model providers"
slug: "vimax-v1-2-0-adds-web-ui-and-new-model-providers"
description: "ViMax has released version 1.2.0, introducing a Web UI and expanding its support for image, video, and chat model providers. The update also includes stability improvements to its Agent Loop and TUI..."
date: 2026-11-27T22:09:22+05:30
tags: [ViMax, VideoGeneration, AIWorkflows, AgenticAI, ModelProviders]
categories: ["AI", "Generative AI", "AI Agents", "Software Development", "Computer Vision"]
image: "https://avatars.githubusercontent.com/u/118165258?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ViMax v1.2.0 adds Web UI and new model providers

ViMax has released version 1.2.0, introducing a Web UI and expanding its support for image, video, and chat model providers. The update also includes stability improvements to its Agent Loop and TUI workflows and the release of a new Novel2Video pipeline.

## 🔍 Overview

ViMax is an agentic video creation framework that connects narrative planning, visual consistency, image generation, video generation, and final assembly in one extensible workflow. This update focuses on enhancing the user interface and integrating new generation models.

## 🧩 How it works

The framework operates through a consistent production pipeline that coordinates references, first frames, camera continuity, and final assembly end to end. It also supports parallelized generation, allowing compatible shots and media assets to be generated concurrently to accelerate multi-shot video production.

## ⚙️ Key details

- **Web UI Features**: The new interface supports named projects, Agent Loop conversations, artifact and storyboard previews, render checkpoints, file uploads, provider settings, and dark mode.
- **Agent Loop and TUI**: A stability update includes stronger LLM retries, persistent render status, landscape image guards, and Script2Video resume fixes. The Agent Loop and TUI workflow is integrated for interactive planning, revision, rendering control, session reuse, and context compaction.
- **Model Providers**: Support added for OpenRouter GPT Image 2 image generation, Seedance 2.0 Fast video generation, Google Omni video generator, and MiniMax chat model.
- **Novel2Video**: A new workflow designed to adapt long-form fiction into episodic visual narratives with narrative compression, character tracking, and scene planning.

## 💡 Capabilities

| Workflow | Description |
| :--- | :--- |
| Idea2Video | Turns a short concept into structured stories, characters, scripts, storyboards, shots, and a finished video. |
| Script2Video | Converts an explicit screenplay into controllable multi-scene, multi-shot video while preserving its creative intent. |
| Novel2Video | Adapts long-form fiction into episodic visual narratives with narrative compression, character tracking, and scene planning. |
| AutoCameo | Places a person or pet from a reference photo into generated stories while maintaining a consistent appearance. |

#ViMax #VideoGeneration #AIWorkflows #AgenticAI #ModelProviders

---

*Source: [HKUDS/ViMax](https://github.com/HKUDS/ViMax)*
