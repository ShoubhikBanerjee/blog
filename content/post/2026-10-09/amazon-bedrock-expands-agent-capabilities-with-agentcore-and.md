---
title: "Amazon Bedrock expands agent capabilities with AgentCore and new frontier models"
slug: "amazon-bedrock-expands-agent-capabilities-with-agentcore-and-new-frontier-models"
description: "Amazon Bedrock has launched new tools and models designed to simplify the development and deployment of enterprise AI agents. This update includes the introduction of AgentCore for managed..."
date: 2026-10-09T22:05:01+05:30
tags: [AmazonBedrock, AIagents, OpenAI, CloudComputing, GenerativeAI]
categories: ["AI", "AI Agents", "Cloud Infrastructure", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/06/ML-22094-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock expands agent capabilities with AgentCore and new frontier models

Amazon Bedrock has launched new tools and models designed to simplify the development and deployment of enterprise AI agents. This update includes the introduction of AgentCore for managed infrastructure, the public preview of Managed Agents powered by OpenAI, and the addition of several high-performance models from partners such as Moonshot AI, xAI, and Anthropic. These enhancements focus on providing enterprise security, auditability through AWS CloudTrail, and more efficient memory management for serverless agents.

## 🔍 Overview

Amazon Bedrock now provides a broader ecosystem for building and connecting AI agents through both managed services and open-source toolkits. Key infrastructure updates include:

* **Amazon Bedrock AgentCore**: Managed infrastructure to build, connect, and deploy agents using any framework or model.
* **Managed Agents**: Now in public preview, these OpenAI-powered agents allow users to keep data within AWS while utilizing existing IAM permissions.
* **Strands**: An open-source toolkit and harness designed for building agents that can run anywhere with 28 percent fewer tokens than popular alternatives.
* **AgentCore Runtime**: Features improved memory management and lower cold start latency, allowing users to pay for actual usage rather than peak memory.

## 🧩 How it works

Building agents for production environments requires addressing architectural challenges such as tool selection and session management. The new capabilities handle these through hardware-isolated environments and specialized models:

* **Decision Modeling**: The Strands Decider 2B is a small, 2B-parameter open-source model that selects between predefined options in approximately 115ms locally, optimizing tasks like tool selection and routing.
* **Session Scaling**: Sessions now scale to zero when idle to manage costs.
* **Human Oversight**: In production designs like Postman’s Agent Mode, agents require user approval before modifying application state.
* **Security Controls**: Amazon Bedrock Guardrails can be used to redact personally identifiable information (PII) before data reaches the underlying large language model.

## ⚙️ Key details

The update introduces a significant variety of new foundation models optimized for different agentic tasks:

| Model | Key Features |
| :--- | :--- |
| GPT-6 Astra | Flagship model with up to 1 million input tokens for complex reasoning |
| GPT-6 Astra Ultrafast | Premium speed tier delivering up to 300 tokens per second |
| Sol (GPT-6 / 6.1) | Designed for coding, computer use, and professional workloads |
| Luna (GPT-6.1) | Optimized for high-volume extraction, summarization, and routing |
| Claude Opus 5.5 | Features adaptive thinking and an effort parameter to bound reasoning depth |
| Claude Sonnet 5.5 | 30 percent lower cost and 30 percent faster than Claude Sonnet 5 |
| Kimi K3 | First open model with 2.8 trillion parameters and native vision |
| Grok 4.6 / 4.7 | 500K token context window with support for self-verification |

## 🚀 Availability

Many of these features and models are available now or in public preview on Amazon Bedrock:

* **Public Preview**: Amazon Bedrock Managed Agents powered by OpenAI.
* **General Availability**: OpenAI Astra, Sol, and Luna models.
* **New Model Additions**: Claude Fable 5.1, Claude Opus 5.5, Claude Sonnet 5.5, Moonshot AI Kimi K3, and xAI Grok 4.6 and 4.7.
* **Open Source**: Strands toolkit, Decider 2B model, and agent harness are available on GitHub and Hugging Face.

## 💡 Why it matters

Moving an agent from a demo to a production environment involves complex engineering, particularly regarding "tool sprawl." Postman found that tool-selection errors increased once a visible toolset exceeded approximately 40 tools. By using Bedrock's managed infrastructure, organizations can scale production workloads without operating their own model-serving infrastructure. This allows for geographically scoped cross-Region inference, model-dependent zero data retention, and multi-tier prompt caching to maintain speed and cost efficiency.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/06/ML-21683-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/06/ML-21683-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/06/ML-21683-5.jpg)

#AmazonBedrock #AIagents #OpenAI #CloudComputing #GenerativeAI

---

*Source: [ICYMI: What landed for AI builders in September 2026 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/icymi-what-landed-for-ai-builders-in-september-2026/)*
*Source: [How Postman runs Agent Mode for 40 million developers on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-postman-runs-agent-mode-for-40-million-developers-on-amazon-bedrock/)*
