---
title: "Tether AI Research Releases BotPsy, a High-Performance 0.8B Agentic Model"
slug: "tether-ai-research-releases-botpsy-a-high-performance-0-8b-agentic-model"
description: "Tether AI Research introduces BotPsy, a 0.8B-parameter model designed for function calling and agentic workflows, built on top of Qwen3.5-0.8B. The model is designed for secure on-device workflows,..."
date: 2026-11-11T18:02:06+05:30
tags: [AIAgents, OpenSource, MachineLearning, FunctionCalling, TetherAIResearch]
categories: ["AI", "Machine Learning", "AI Agents", "Open Source Models", "Function Calling"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6468b319b2321e47d3267049/Emr86qw6NAueYLdIEiTTD.png"
author: "Shoubhik Banerjee"
draft: false
---

# Tether AI Research Releases BotPsy, a High-Performance 0.8B Agentic Model

Tether AI Research introduces BotPsy, a 0.8B-parameter model designed for function calling and agentic workflows, built on top of Qwen3.5-0.8B. The model is designed for secure on-device workflows, providing exceptional instruction-following reliability and efficiency while keeping user data private.

## 🔍 Overview
BotPsy is a 'personal assistant' that uses tools to perform a variety of simple tasks for the user. Its capabilities span domains such as:

*   Web search & research
*   Travel & lifestyle
*   Commerce & finance
*   Business & customer operations
*   Device & vehicle control
*   Files & documents
*   Calendar
*   Email & messaging

## 📊 Performance Benchmarks
BotPsy achieves state-of-the-art (SOTA) tool-use and agentic performance for its size, outperforming every model of up to 1.2B parameters that was tested. It also outperforms the larger Qwen3.5-2B-Think model on several key metrics.

| Benchmark | BotPsy Score | vs Base Model | vs Qwen3.5-2B-Think |
| :--- | :--- | :--- | :--- |
| **BFCL v4** | 44.0 | +20.6 | +6.3 |
| **ACEBench** | 58.7 | +28.6 | +3.3 |
| **τ-bench** | 51.5 | +28.3 | +5.0 |
| **ToolSandbox** | 64.6 | N/A | +23.4 |
| **BrowseComp-Plus** | 4.5 | N/A | +1.7 |
| **τ²-bench (Telecom)** | 82.5 | N/A | +13.2 |
| **Hallucination (BFCL)** | 86.1 | N/A | N/A |
| **Incomplete Cases (ACEBench)** | 51.3 | +37.6 | N/A |
| **IFEval** | 90.8 | +31.1 | N/A |
| **IFBench** | 55.9 | +33.9 | N/A |
| **GPQA Diamond** | 38.1 | +4.9 | N/A |
| **MMLU-Pro** | 48.9 | +7.3 | N/A |

BotPsy roughly doubles the agentic capability of its base model on key benchmarks. It also demonstrates superior efficiency, using about 3× fewer reasoning tokens on GPQA Diamond and 2.7× fewer on MMLU-Pro compared to its base model.

## ⚙️ Availability & Deployment
BotPsy will be released with open weights under the Apache 2.0 license for research and educational use. It is available in three precisions (bf16, Q8, Q4) as Hugging Face safetensors and as GGUF files for the QVAC SDK and l.

## ⚠️ Limitations
As a small model, BotPsy still makes mistakes and is not intended for high-stakes use. Due to its small parameter count, it is best suited to tasks of low to medium difficulty. In automated red-teaming, it produces unsafe responses 21% of the time, which is the lowest rate of all models of up to 1.2B parameters tested.

![figure](https://cdn-uploads.huggingface.co/production/uploads/63aa76c43453852ef544bfa7/bcUf3apeKkPJWAx-JeaDQ.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/63aa76c43453852ef544bfa7/880caLxnAH9jssZK8Gaks.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6158408ecc7a50d79f912a63/ChexLcqHGtdol8zF2em6b.png)

#AIAgents #OpenSource #MachineLearning #FunctionCalling #TetherAIResearch

---

*Source: [BotPsy: On-Device Personal Assistant with a Sub-Billion-Parameter Agentic Language Model](https://huggingface.co/blog/qvac/botpsy)*
