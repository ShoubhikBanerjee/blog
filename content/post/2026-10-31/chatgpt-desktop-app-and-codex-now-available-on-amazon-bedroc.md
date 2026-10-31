---
title: "ChatGPT Desktop App and Codex Now Available on Amazon Bedrock GovCloud (US)"
slug: "chatgpt-desktop-app-and-codex-now-available-on-amazon-bedrock-govcloud-us"
description: "The ChatGPT desktop app is now available on Amazon Bedrock in AWS GovCloud (US). The deployment gives organizations access to OpenAI’s frontier models through two components and adds a..."
date: 2026-10-31T06:04:25+05:30
tags: [ChatGPT, AmazonBedrock, GovCloud, AIcoding]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Developer Tools", "Security"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22175-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# ChatGPT Desktop App and Codex Now Available on Amazon Bedrock GovCloud (US)

The ChatGPT desktop app is now available on Amazon Bedrock in AWS GovCloud (US). The deployment gives organizations access to OpenAI’s frontier models through two components and adds a controlled, GovCloud‑compatible coding agent called Codex.

## 🔍 Overview
- The app runs on an organization‑managed computer via the desktop app or the Codex CLI.
- Model inference is routed through the **Responses API** on Amazon Bedrock.
- All processing stays within the selected Amazon Bedrock AWS Region, satisfying data‑residency requirements.

## 🧩 How it works
- **Authentication** – The app supports two Amazon Bedrock authentication pathways: an Amazon Bedrock API key **or** the AWS SDK credential chain.  
  - AWS SSO through AWS IAM Identity Center works with the credential‑chain pathway.
  - The app first checks for `AWS_BEARER_TOKEN_BEDROCK` in its environment (set via `%USERPROFILE%\.codex\.env` on Windows or `~/.codex/.env` on Linux/macOS).  
  - If no bearer token is present, it falls back to the standard AWS SDK credential chain (Windows defaults: `%USERPROFILE%\.aws\credentials` and `%USERPROFILE%\.aws\config`).
- **Routing** – Requests are sent to the Amazon Bedrock Mantle endpoint in `us-gov-west-1`.  
  - Access is governed by AWS Identity and Access Management (IAM) and existing GovCloud network controls.
- **Security posture** – The configuration uses API‑mode sign‑in, a managed device policy, a named AWS profile (`codex-il5`), and network restrictions that allow only the approved Bedrock endpoint while disabling other external connections.
- **Deployment steps** –
  1. Set up authentication (API key or credential chain).
  2. Create the `requirements.toml` and `config.toml` files for the desktop app.
  3. Launch, initialize, and verify the deployment.

## ⚙️ Key details
- **Components**
  | Component | Role |
  |---|---|
  | ChatGPT desktop app | Sends inference requests to Bedrock and provides UI/CLI access |
  | Codex CLI | OpenAI coding agent for developing, testing, and reviewing software |
- **Capabilities**
  - Handles complex, multi‑step tasks and delivers review‑ready results.
  - Optimized for long‑horizon developer workflows with GPT‑powered inference.
  - Integrated IDE support for Visual Studio Code, JetBrains, and Xcode.
- **Pricing & data handling**
  - Pay‑per‑token; no seat licenses and no per‑developer commitments.
  - Zero Data Retention (ZDR) mode available: prompts and responses are processed without being written to durable storage by AWS or shared with model providers.

## 🚀 Availability
- The controlled local deployment targets **AWS GovCloud (US‑West)** (`us-gov-west-1`).
- Organizations can use the app wherever GovCloud identities, endpoints, and regional controls are required.

## 💡 Why it matters
- Provides a secure, GovCloud‑compatible way for developers to leverage OpenAI’s latest models without leaving the AWS environment.
- Enables enterprises with strict data‑residency and compliance needs to run AI‑assisted coding workloads at scale.
- Consolidates authentication and permission management under existing AWS IAM and network policies, reducing operational overhead.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22175-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22175-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22175-3.jpg)

#ChatGPT #AmazonBedrock #GovCloud #AIcoding

---

*Source: [Configure the ChatGPT desktop app with Amazon Bedrock in AWS GovCloud (US) | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/configure-the-chatgpt-desktop-app-with-amazon-bedrock-in-aws-govcloud-us/)*
