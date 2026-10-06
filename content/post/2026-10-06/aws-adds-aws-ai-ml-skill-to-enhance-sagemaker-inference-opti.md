---
title: "AWS adds aws‑ai‑ml skill to enhance SageMaker inference optimization"
slug: "aws-adds-awsaiml-skill-to-enhance-sagemaker-inference-optimization"
description: "Amazon SageMaker AI optimized generative AI inference now includes the aws‑ai‑ml skill, available through the Agent Toolkit for AWS."
date: 2026-10-06T18:04:10+05:30
tags: [SageMaker, AIInference, CodingAgents]
categories: ["AI", "Machine Learning", "Cloud Computing", "AI Agents", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21968-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS adds aws‑ai‑ml skill to enhance SageMaker inference optimization

Amazon SageMaker AI optimized generative AI inference now includes the aws‑ai‑ml skill, available through the Agent Toolkit for AWS.

## 🔍 Overview
- Engineers increasingly use coding assistance tools to accelerate development workflows.
- The new aws‑ai‑ml skill gives coding agents deep expertise in inference optimization and benchmarking.

## 🧩 How it works
- The skill plugs into any coding agent that supports the Model Context Protocol (MCP), turning it into a SageMaker AI inference optimization expert.
- Supported agents include Kiro, Claude Code, and Codex.
- Agents can discover and load the skill at runtime (Kiro and Claude Code) via the AWS MCP Server without local installation.

## ⚙️ Key details
- **Capabilities:**
  - Benchmark endpoints
  - Recommend deployment configurations
  - Compare performance runs
  - Generate executable SageMaker Python SDK v3 code
- **SageMaker AI inference supports:**
  - Serverful hosting across real‑time, batch, and asynchronous modes
  - On‑demand and reserved capacity
  - Heterogeneous instances, VPC isolation, automatic scaling
  - Integration with every SageMaker AI training path

## 🚀 Availability & Installation
**Local machine**
1. Install the Agent Toolkit for AWS (requires AWS CLI 2.35+ and `uv`). It auto‑detects agents, installs skills, and configures the AWS MCP Server.
2. Install the aws‑ai‑ml skill.
3. Open the coding agent’s chat panel and ask “What skills are available?” to confirm the skill is listed.

**SageMaker Studio**
1. Open Amazon SageMaker Studio in the target AWS account and region.
2. Create a private JupyterLab space (e.g., `my‑inference‑opt`).
3. Select the image that includes the SageMaker AI optimized generative AI inference skill; the image ships pre‑configured with the aws‑ai‑ml skill and dependencies.
4. Run the space (first boot takes 5–10 minutes).

**Prerequisites**
- AWS credentials with permissions to call SageMaker AI APIs (create endpoints, run benchmark and recommendation jobs).
- No additional IAM configuration is required for the skill itself; generated code runs under your credentials.

## 💡 Why it matters
- Provides instant, expert‑level inference optimization without manual tuning.
- Reduces time from concept to a working conversation to roughly 10 minutes.
- Leverages existing coding agents, extending their utility in ML workflows.

#SageMaker #AIInference #CodingAgents

---

*Source: [New agent skill: Amazon SageMaker optimized generative AI inference for your coding agent | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/new-agent-skill-amazon-sagemaker-optimized-generative-ai-inference-for-your-coding-agent/)*
