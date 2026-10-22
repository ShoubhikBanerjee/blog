---
title: "Adaptive Agentic Intelligence Framework Combines Local SLMs and Cloud Models"
slug: "adaptive-agentic-intelligence-framework-combines-local-slms-and-cloud-models"
description: "The Adaptive Agentic Intelligence Framework (AAIF), built with Strands Agents, introduces an orchestration framework that combines local small language models (SLMs) with cloud-hosted models in..."
date: 2026-10-22T18:03:17+05:30
tags: [AAIF, StrandsAgents, AmazonBedrock, EdgeAI, SLM]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing", "Edge Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-19699-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Adaptive Agentic Intelligence Framework Combines Local SLMs and Cloud Models

The Adaptive Agentic Intelligence Framework (AAIF), built with Strands Agents, introduces an orchestration framework that combines local small language models (SLMs) with cloud-hosted models in Amazon Bedrock. Based on research from Belcak et al. at NVIDIA, AAIF replaces the standard approach of routing every request to a single large, expensive model by handling routine tasks locally and sending complex analysis to the cloud.

## 🔍 Overview

AAIF uses an Internet of Things (IoT) monitoring scenario as a reference implementation to demonstrate how model orchestration reduces costs while maintaining low latency for local operations. The architecture can run across several environment types:

* **Edge devices:** Devices such as a Raspberry Pi with 8 GB of memory.
* **Full cloud deployments:** Setup where all inference is routed to Amazon Bedrock.
* **Hybrid configurations:** Architecture combining local execution speed with cloud reasoning.

## 🧩 How it works

AAIF organizes AI processing into three distinct layers using a local SLM orchestrator (`llama3.2:1b`) running through Ollama. The orchestrator classifies incoming user requests dynamically without hardcoded keyword rules and dispatches them to specific tools.

| Tool Name | Processing Location | Function | Model / Provider |
| --- | --- | --- | --- |
| `get_device_telemetry` | Local | Local sensor data retrieval | Strands Agent |
| `analyze_camera_feed` | Local | On-device vision processing without sensitive camera feeds leaving the device | `llama3.2-vision` via Ollama |
| `get_expert_insights` | Cloud | Complex pattern analysis and strategic recommendations | Amazon Bedrock via `boto3` |

## ⚙️ Key details

Setting up the framework reference implementation requires the following components and dependencies:

* **Environment:** Python 3.10+ installed.
* **Local Models:** `ollama pull llama3.2:1b` (orchestrator) and `ollama pull llama3.2-vision` (vision analysis).
* **Python Packages:** Installed via `pip install strands-agents strands-agents-tools` and `pip install boto3`.
* **Tool Definition:** Strands Agents uses the `@tool` decorator to define capabilities invoked by agents.
* **Flexibility:** Separates routing logic from processing tools, allowing tools to be swapped or reconfigured independently based on network connectivity and hardware.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-19699-1.png)

#AAIF #StrandsAgents #AmazonBedrock #EdgeAI #SLM

---

*Source: [Adaptive agentic intelligence framework using Strands Agents | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/adaptive-agentic-intelligence-framework-using-strands-agents/)*
