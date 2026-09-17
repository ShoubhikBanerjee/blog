---
title: "Serverless Framework V.4 Updates and New AI Integration Features"
slug: "serverless-framework-v-4-updates-and-new-ai-integration-features"
description: "Serverless Inc. continues to maintain the Serverless Framework, with V.4 featuring significant updates as of July 2026 to simplify the deployment of code and cloud infrastructure."
date: 2026-09-17T18:02:05+05:30
tags: [Serverless, AWS, CloudInfrastructure, AIagents, IaC]
categories: ["AI", "Cloud Computing", "Software Development", "AI Infrastructure"]
image: "https://avatars.githubusercontent.com/u/13742415?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Serverless Framework V.4 Updates and New AI Integration Features

Serverless Inc. continues to maintain the Serverless Framework, with V.4 featuring significant updates as of July 2026 to simplify the deployment of code and cloud infrastructure.

## 🔍 Overview
The Serverless Framework is a multi-language command-line tool using YAML syntax to build auto-scaling applications that cost nothing when idle. It supports Node.js, Typescript, Python, Go, and Java, and is extensible via over 1,000 plugins.

## ⚙️ Key Details

| Feature | Description |
| :--- | :--- |
| Sandboxes | Isolated, ephemeral compute on AWS Lambda for workloads like AI agents and code execution |
| Amazon Bedrock AgentCore Support | Define AI agents, memory, tools, gateways, browsers, and code interpreters in `serverless.yml` via the `ai` property |
| Managed Instances | EC2-backed Lambda execution for higher throughput and long-running workloads |
| Durable Functions | Built-in support for stateful workflows and long-running orchestrations |
| Serverless MCP | Integration for AI-powered IDEs (Cursor, Windsurf) to debug apps by fetching logs, state, and config from AWS |
| Lambda tenant isolation mode | Distinct compute environments per tenant to reduce noisy neighbor effects |
| HTTP response streaming | Stream logs, reports, or AI LLM responses from Lambda with API Gateway HTTP APIs |
| AWS Login & SSO | Browser-based credential setup via `serverless login aws` and `serverless login aws sso` |
| Deployment Diffs | Preview live AWS CloudFormation stack changes using `serverless diff` |
| Reconcile Command | Sync usage records with AWS accounts when stacks are removed outside the CLI |
| Per-function IAM roles | Ability to add per-function IAM policies |

## 🧩 How it works
The framework provides integrated support for several Infrastructure as Code (IaC) project files, allowing users to deploy AWS SAM, AWS CloudFormation, and traditional Serverless Framework projects with one tool. 

Additional integrated capabilities include:
* **Built-in plugins:** Former community plugins such as AppSync, Prune, API Gateway Service Proxy, and Python requirements are now first-class features.
* **Custom Domain Support:** Automatic configuration of custom domains and SSL certificates is now built into the CLI.
* **Doppler Integration:** Secrets can be fetched from Doppler via Serverless Framework Variables.

#Serverless #AWS #CloudInfrastructure #AIagents #IaC

---

*Source: [serverless/serverless](https://github.com/serverless/serverless)*
