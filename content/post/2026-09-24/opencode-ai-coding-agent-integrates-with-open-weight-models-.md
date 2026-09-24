---
title: "OpenCode AI Coding Agent Integrates with Open Weight Models on Amazon Bedrock"
slug: "opencode-ai-coding-agent-integrates-with-open-weight-models-on-amazon-bedrock"
description: "OpenCode is an open source, terminal-native AI coding agent built in Go that now pairs with open weight models on Amazon Bedrock to provide a locally running assistant with secure cloud inference."
date: 2026-09-24T22:03:57+05:30
tags: [OpenCode, AmazonBedrock, OpenSourceAI, AICodingAgent, AWS]
categories: ["AI", "AI Agents", "Software Development", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/22/ML-21055-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# OpenCode AI Coding Agent Integrates with Open Weight Models on Amazon Bedrock

OpenCode is an open source, terminal-native AI coding agent built in Go that now pairs with open weight models on Amazon Bedrock to provide a locally running assistant with secure cloud inference.

## 🧩 How it works
OpenCode manages coding tasks through the following capabilities:
* Reads and edits files
* Runs shell commands
* Understands project structure using Language Server Protocol (LSP) diagnostics
* Connects to over 75 LLM providers, including Amazon Bedrock

## ⚙️ Key details
Amazon Bedrock provides serverless access to open weight models where code, prompts, and responses remain within the user's AWS account. The service does not use inputs or outputs to train foundation models.

| Feature | Detail |
| :--- | :--- |
| Compliance | HIPAA, SOC 2, ISO 27001, FedRAMP, and GDPR |
| Security | Inherits IAM policies, CloudTrail logging, PrivateLink connectivity, and encryption controls |
| Scalability | Default limits of 100M tokens per minute and 10K requests per minute |
| Model Switching | Single API parameter change |

### Cost Tiers
* **Priority**: For latency-sensitive production
* **Standard**: On-demand inference (pay per token)
* **Flex**: 50 percent lower cost for variable-latency workloads

## 🚀 Availability
Users can utilize specific models and profiles on Bedrock:
* **Kimi K3**: A model that reasons before answering (depth set via `reasoning_config` as low, high, or max). It can be invoked via:
    * `global.moonshotai.kimi-k3`: A global profile routing requests worldwide, costing approximately 10% less than a geographic profile.
    * `us.moonshotai.kimi-k3`: A US geographic profile for data residency requirements.
* **Other Models**: Practical examples include OpenAI GPT-OSS 120B and NVIDIA Nemotron 3 Super 120B.

## 💡 Why it matters
Recent industry reports and benchmarks highlight the shift toward open weight models and agentic workflows:
* **Adoption**: According to McKinsey’s 2025 report, 76 percent of organizations expect to increase open source AI usage, and leading adopters are 40 percent more likely to use open weight models.
* **Performance**: CrowdStrike’s fine-tuned NVIDIA Nemotron achieved 96% valid query accuracy, outperforming Claude Sonnet 4.5 (94%) and GPT-4o (61%).
* **Cost**: Gartner’s 2026 analysis states agentic workflows multiply token consumption 5–30x, making cost-per-token critical.
* **Evaluation**: The Artificial Analysis Coding Index benchmarks real-world tasks (SWE-Bench, Terminal-Bench, SWE-Atlas), and Amazon Bedrock Evaluations allows for side-by-side comparisons using human review, LLM-as-a-judge, or automatic scoring.

#OpenCode #AmazonBedrock #OpenSourceAI #AICodingAgent #AWS

---

*Source: [Use open weight models as your AI coding agent with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/use-open-weight-models-as-your-ai-coding-agent-with-amazon-bedrock/)*
