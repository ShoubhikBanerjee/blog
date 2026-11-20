---
title: "Kimi Code CLI v2.7 Adds Native Amazon Bedrock Integration"
slug: "kimi-code-cli-v2-7-adds-native-amazon-bedrock-integration"
description: "- Kimi Code CLI is an open source coding agent from Moonshot AI."
date: 2026-11-20T14:26:01+05:30
tags: [AWS, AmazonBedrock, KimiCodeCLI, OpenSourceAI, AIagents]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Open Source"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22481-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Kimi Code CLI v2.7 Adds Native Amazon Bedrock Integration

## 🔍 Overview
- Kimi Code CLI is an open source coding agent from Moonshot AI.
- v2.7.0 introduces a native Amazon Bedrock provider.
- The CLI can now use the standard AWS credential chain, named profiles, and SSO instead of a separate API key.
- Example model: Kimi K3.1 Pro Highspeed – streaming, configurable reasoning, image input, client-side tool calling.
## 🧩 How it Works
- The bedrock provider resolves temporary credentials through the AWS CLI credential chain.
- It infers the API format and regional endpoint from the model ID, and can be overridden.
- The provider uses @aws/bedrock-token-generator to create a short-term Amazon Bedrock API key, renewed automatically.
- No AWS access key or Bedrock key is required in config.toml; an explicit key via `api_key` or `api_key_env` takes precedence if supplied.
- The provider resolves `AWS_REGION` or `AWS_DEFAULT_REGION` and builds the bedrock-runtime endpoint.
- For Kimi models, this resolves to the OpenAI-compatible Chat Completions path.
- The model alias maps to a Bedrock model or inference profile ID, e.g., `global.moonshotai.kimi-k3.1` (global. prefix selects the profile, AWS_REGION determines regional endpoint).
- The CLI streams responses and can use client-side tool-calling during coding tasks.
- Ephemeral API keys generated are valid for up to 12 hours or the AWS session length, whichever is shorter.
## ⚙️ Key Details
| Feature | Detail |
|---------|--------|
| Provider type | native Bedrock |
| Credential method | AWS credential chain, named profiles, SSO |
| Token generator | @aws/bedrock-token-generator |
| Endpoint inference | From model ID, override possible |
| Model alias | Maps to Bedrock inference profile |
| Example profile | `global.moonshotai.kimi-k3.1` |
| Example model | Kimi K3.1 Pro Highspeed |
| Availability | global cross-Region inference |
| Key validity | up to 12 h or AWS session length |
| AWS CLI requirement | v2.32.0 or later |
## 🚀 Availability
- Requires Kimi Code CLI v2.7.0 or later.
- Optional AWS login workflow needs AWS CLI v2.32.0 or later.
- An IAM identity (user or assumed role) must have permission to invoke the target model and inference profile in the chosen AWS Region.

#AWS #AmazonBedrock #KimiCodeCLI #OpenSourceAI #AIagents

---

*Source: [Use Kimi Code CLI with models on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/use-kimi-code-cli-with-models-on-amazon-bedrock/)*
