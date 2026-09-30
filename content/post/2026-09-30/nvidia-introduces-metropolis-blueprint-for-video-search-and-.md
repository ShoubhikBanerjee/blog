---
title: "NVIDIA Introduces Metropolis Blueprint for Video Search and Summarization 3.3"
slug: "nvidia-introduces-metropolis-blueprint-for-video-search-and-summarization-3-3"
description: "NVIDIA has released the Metropolis Blueprint for Video Search and Summarization (VSS), providing developers with agent skills to accelerate the creation of visual AI agents. The system integrates..."
date: 2026-09-30T12:02:09+05:30
tags: [NVIDIA, Metropolis, VLM, AIagents, ComputerVision]
categories: ["AI", "Computer Vision", "AI Agents", "Software Development"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/robotics-press-nurec-devpage-kv-1600x900-1-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces Metropolis Blueprint for Video Search and Summarization 3.3

NVIDIA has released the Metropolis Blueprint for Video Search and Summarization (VSS), providing developers with agent skills to accelerate the creation of visual AI agents. The system integrates vision-language models (VLMs), large language models (LLMs), retrieval-augmented generation (RAG), and Model Context Protocol (MCP) tools to convert recorded and live video into automated reporting, verified alerts, visual Q&A, and natural-language search.

## 🧩 How it works

VSS 3.3 organizes its capabilities into tools, benchmarks, operation skills, and deployment skills. VSS Agent Skills allow coding agents—such as Codex, Claude Code, or any agentskills.io-compatible agent—to operate and deploy VSS using natural-language requests.

Central to the deployment is the Build Vision Agent skill (`vss-build-vision-ai`), which combines VSS workflows into a single application for use cases like traffic management or SOP compliance. This skill:
* Maps application goals to required microservices and VSS workflows.
* Combines workflows such as summarization, search, and alerting into one deployment plan.
* Reuses shared infrastructure including Redis, Kafka, Elasticsearch, VIOS, MCP services, and HAProxy ingress.
* Generates a self-contained build consisting of a `compose.yml`, a resolved.yml (a flattened Compose file), and `_builds/<name>/override.env` containing the Foundation and effective Compose profiles.

## ⚙️ Key details

The Build Vision Agent skill begins with one of four validated developer profiles:

| Profile | Capability |
| :--- | :--- |
| base | VLM dense captioning and Q&A on clips |
| alerts | Real-time VLM alerting, or RT-CV detection with behavior analytics and VLM alert verification |
| lvs | Long video summarization |
| search | Object and video embeddings with agentic search |

Additionally, VSS 3.3 introduces Adaptive Efficient Video Sampling (EVS) to reduce runtime costs. While a fixed pruning rate version of EVS already exists in Cosmos NIM microservices and vLLM, the adaptive version in VSS 3.3 is integrated into the real-time VLM microservice to decide which tokens to keep per frame and per patch. It reduces redundant processing by batching VLM work around events and pruning visual tokens for parts of a frame that remain unchanged from the previous one.

## 💡 Why it matters

The combination of the Build Vision Agent skill and Adaptive EVS reduces costs during both composition and runtime:
* **Faster Deployment:** A bottling-line overflow agent can be built and deployed in under 30 minutes using a single prompt and a few dollars of coding-agent usage.
* **Reduced Processing:** Adaptive EVS provides 46% more concurrent streams on the same GPU and 80% fewer VLM input tokens for a 60-minute summary.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/05/metropolis-vss-blueprint-gif.gif)

#NVIDIA #Metropolis #VLM #AIagents #ComputerVision

---

*Source: [Lower the Cost of Building and Running Visual AI Agents with NVIDIA VSS Blueprint 3.3 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/lower-the-cost-of-building-and-running-visual-ai-agents-with-nvidia-vss-blueprint-3-3/)*
