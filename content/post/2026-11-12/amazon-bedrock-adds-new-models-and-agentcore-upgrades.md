---
title: "Amazon Bedrock adds new models and AgentCore upgrades"
slug: "amazon-bedrock-adds-new-models-and-agentcore-upgrades"
description: "Amazon Bedrock announced a set of updates that add new large‑language models, expand AgentCore tooling, and improve pricing and performance across its AI services."
date: 2026-11-12T06:14:14+05:30
tags: [AmazonBedrock, AIModels, AgentCore, Claude, OpenAI]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Natural Language Processing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-22436-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock adds new models and AgentCore upgrades

Amazon Bedrock announced a set of updates that add new large‑language models, expand AgentCore tooling, and improve pricing and performance across its AI services.

## 🔍 Overview
- Amazon Bedrock now provides access to leading models and the tools to build and scale AI applications securely.
- The platform is extended with Amazon Bedrock AgentCore for building, connecting, and optimizing agents.

## 🤖 New Models
- **Claude Haiku 5.5** – built for subagents and high‑volume, cost‑sensitive work; 75 % cheaper than Claude Haiku 4.5; first Haiku with effort controls to tune cost against intelligence.
- **OpenAI GPT‑6.1 Terra** – generally available; matches GPT‑6 Astra on the Agents’ Last Exam and completes tasks >3 × faster than GPT‑6 Astra and GPT‑6.1 Sol; token prices ≥50 % lower than GPT‑6.1 Sol and GPT‑5.6 Terra; accepts text and images up to 1 million tokens; Ultrafast mode for real‑time coding assistants.
- **Amazon Nova 2.5 Sonic** – speech‑to‑speech model that improves reasoning, instruction following, and tool‑calling accuracy; lower latency at the same price as Amazon Nova 2.
- **GLM 5.3 (Z.ai)** – open‑weight model for agentic coding and long‑horizon software engineering; 1‑million‑token context window and prompt caching; limited to eligible enterprise customers.
- **TwelveLabs Pegasus 1.5** – converts entire videos into structured, time‑coded metadata; reads visuals, audio, and on‑screen text in a single pass with no separate ingestion pipeline.

## 📊 Model Highlights
| Model | Key Highlights |
|---|---|
| Claude Haiku 5.5 | Subagents, 75 % cost reduction vs 4.5, effort controls |
| GPT‑6.1 Terra | >3 × faster than GPT‑6 Astra, ≥50 % cheaper tokens, 1 M token multimodal input |
| Nova 2.5 Sonic | Better reasoning & tool‑calling, lower latency, same price |
| GLM 5.3 | Open‑weight, 1 M token window, prompt caching |
| Pegasus 1.5 | Video‑to‑metadata, single‑pass visual/audio/text analysis |

## ⚙️ AgentCore Enhancements
- **AgentCore CLI** v1.0 GA: faster startup, consistent command structure, supports more resources; existing projects upgrade with a single command.
- **AgentCore Gateway** now supports Amazon Bedrock `InvokeModel` APIs and model fallback; can route requests to alternate models when the primary is throttled or unreachable; includes a circuit‑breaker and VPC private‑target support.
- Integration with **AWS Step Functions** allows agents to invoke Standard or Express workflows as tools; the agent decides when to run a workflow and Step Functions executes each step as defined.

## 💰 Pricing & Performance
- Claude Haiku 5.5 costs around 75 % less than Claude Haiku 4.5.
- GPT‑6.1 Terra token prices are at least 50 % lower than GPT‑6.1 Sol and GPT‑5.6 Terra.
- Nova 2.5 Sonic offers lower latency at the same price as Nova 2.

## 🚀 Availability
- Claude Haiku 5.5, GPT‑5.6 models with cross‑Region inference, and Daybreak Red (security‑focused model) are now in AWS GovCloud (US) and AWS GovCloud (US‑East) for eligible customers.
- GLM 5.3 is available to eligible enterprise customers.
- Structured outputs (schema‑compliant JSON) are now available for all Claude models on Amazon Bedrock.

## 💡 Why It Matters
- Faster, cheaper, and higher‑capacity models enable more extensive AI workloads such as large‑scale agent orchestration, multimodal content creation, and real‑time assistance.
- AgentCore’s new CLI, Gateway, and Step Functions integration simplify building production‑grade AI agents that can fail‑over between models and operate securely within VPCs.
- Structured JSON outputs reduce integration effort, allowing developers to consume model responses without custom parsing or retries.


#AmazonBedrock #AIModels #AgentCore #Claude #OpenAI

---

*Source: [ICYMI: What landed for AI builders in October 2026 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/icymi-what-landed-for-ai-builders-in-october-2026/)*
