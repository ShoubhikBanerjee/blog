---
title: "Epsilon Deploys Intent‑Driven UI Testing with Amazon Nova Act and Bedrock AgentCore Browser"
slug: "epsilon-deploys-intentdriven-ui-testing-with-amazon-nova-act-and-bedrock-agentcore-browser"
description: "Epsilon, the data, technology, and marketing‑services firm in Publicis Groupe, has extended its shared Agentic Platform to offer intent‑driven UI testing as a managed service. By wiring..."
date: 2026-10-30T21:54:47+05:30
tags: [AmazonWebServices, AIagents, IntentTesting, UIAutomation]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Software Testing", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21285-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Epsilon Deploys Intent‑Driven UI Testing with Amazon Nova Act and Bedrock AgentCore Browser

Epsilon, the data, technology, and marketing‑services firm in Publicis Groupe, has extended its shared Agentic Platform to offer intent‑driven UI testing as a managed service. By wiring Amazon Nova Act to the Amazon Bedrock AgentCore Browser tool, the company can run natural‑language test workflows on isolated browser instances without the operational overhead of managing binaries or display servers.

## 🔍 Overview
- Goal: layer intent‑based testing on top of an existing Playwright regression suite.
- Requirements evaluated: natural‑language test authoring and managed, multi‑tenant browser infrastructure.
- Outcome: a three‑component service that lets product teams create, execute, and audit UI tests in their own AWS accounts.

## 🧩 How it works
1. **Create a workflow** – A user calls the platform API with a `target_url` and an ordered list of plain‑English steps.
2. **Register with Nova Act** – The platform registers a Nova Act workflow definition on AWS.
3. **Execute** – A background task runner (Celery) launches an Amazon Bedrock AgentCore Browser session.
   * Each step is sent to Nova Act, which drives the browser via a Chrome DevTools Protocol (CDP) WebSocket.
   * Conditional logic (e.g., *"if a tour box appears, skip it"*) is supported.
4. **Capture & store** – For every step a screenshot is taken, pass/fail is recorded, an overall pass rate is computed, and the results JSON, screenshots, and session ID are saved to Amazon S3.
5. **Completion hook** – The result is written back to the platform for reporting.

## ⚙️ Key Details
- **Shared infrastructure** built by the Agentic Platform team (50 engineers) provides:
  - Skills‑based agent builder
  - Federated identity & pre‑flight authorization
  - Model Context Protocol (MCP) integration
  - Cross‑account provisioning
- **Amazon Bedrock AgentCore Browser Tool** gives:
  - Isolated browser instances (no binaries, no display server)
  - Live view for human takeover (CAPTCHA, MFA)
  - Session recording to Amazon S3
  - AWS CloudTrail audit logs
- **Authentication & tenancy**
  - Nova Act uses the standard AWS credential chain (task role).
  - Teams provision via AWS STS `AssumeRole`; each team runs tests in its own AWS account under a scoped role.
- **Why it mattered** – With hundreds of millions of consumer profiles and thousands of brand relationships, Epsilon needed UI testing that could keep pace with rapid application changes while removing the operational burden of managing browser infrastructure.

## 🚀 Availability
The intent‑driven testing service is now available to all product teams on Epsilon’s Agentic Platform. Teams can start by defining a workflow through the platform API and executing it in their own AWS account.

## 💡 Why it matters
- **Operational efficiency** – Eliminates the need to ship and maintain browser binaries or display servers.
- **Scalable multi‑tenant model** – Each team operates within its own AWS account, preserving security isolation.
- **Natural‑language authoring** – Engineers can author tests in plain English, complementing existing selector‑based Playwright tests.
- **Full auditability** – CloudTrail logs and session recordings provide traceability for compliance and debugging.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21285-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21285-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21285-3.jpg)

#AmazonWebServices #AIagents #IntentTesting #UIAutomation

---

*Source: [Building intent-driven UI testing with Amazon Nova Act | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/building-intent-driven-ui-testing-with-amazon-nova-act/)*
*Source: [How MoEngage turned over 400 APIs into agent tools with AgentCore Gateway | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-moengage-turned-over-400-apis-into-agent-tools-with-agentcore-gateway/)*
