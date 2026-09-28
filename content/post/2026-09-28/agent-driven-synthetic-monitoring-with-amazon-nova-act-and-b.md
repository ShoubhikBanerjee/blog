---
title: "Agent-Driven Synthetic Monitoring with Amazon Nova Act and Bedrock AgentCore"
slug: "agent-driven-synthetic-monitoring-with-amazon-nova-act-and-bedrock-agentcore"
description: "AWS has introduced an agent-driven approach to synthetic monitoring that utilizes Amazon Nova Act and Amazon Bedrock AgentCore to emulate real user journeys through automated transactions."
date: 2026-09-28T22:02:06+05:30
tags: [AmazonNovaAct, AmazonBedrock, SyntheticMonitoring, LLM, AWS]
categories: ["AI", "AI Agents", "Cloud Computing", "Software Testing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/03/ML-20230-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Agent-Driven Synthetic Monitoring with Amazon Nova Act and Bedrock AgentCore

AWS has introduced an agent-driven approach to synthetic monitoring that utilizes Amazon Nova Act and Amazon Bedrock AgentCore to emulate real user journeys through automated transactions.

## 💡 Why it matters
Traditional browser automation frameworks, such as Playwright and Selenium, rely on explicit selectors and Document Object Model (DOM) locators, which can lead to brittleness. Amazon Nova Act addresses this by using a multimodal large language model (LLM) that processes UI screenshots rather than DOM selectors.

Key advantages include:
- **Resilience**: Because the model reasons from what it sees on screen rather than element IDs or CSS classes, it adapts to styling changes without requiring script updates.
- **Performance**: In early enterprise customer use cases, Amazon Nova Act has demonstrated over 90% accuracy on browser workflows.

## 🧩 How it works
Amazon Nova Act defines and executes UI workflows using orchestration logic combined with natural-language actions. The technical workflow is managed as follows:

| Component | Role |
| :--- | :--- |
| Amazon EventBridge Scheduler | Triggers synthetic monitoring runs on a defined schedule (every 5 minutes to hourly) via the universal target capability. |
| Amazon Bedrock AgentCore Runtime | Provides serverless execution with session isolation and stable invocation endpoints. |
| AgentCore Browser tool | Provides a secure, isolated remote browser environment for each test run. |
| Amazon Nova Act | Drives the UI workflow using natural-language actions within the browser session. |
| Amazon SNS | Delivers failure notifications to subscribed endpoints (email, chat integrations, incident response tooling) if a journey fails. |

## ⚙️ Key details
To implement this architecture, the following requirements are necessary:

**AWS Account Access**
- Amazon Nova Act
- Amazon Bedrock AgentCore (Runtime and Browser tool)
- Amazon Elastic Container Registry (Amazon ECR)
- IAM
- Amazon EventBridge Scheduler
- Amazon SNS

**Technical Prerequisites**
- Python 3.11 or later
- Docker
- AWS Command Line Interface (AWS CLI) v2 configured with credentials
- Node.js 18 or later and AWS Cloud Development Kit (AWS CDK) for the production infrastructure path (a standalone deploy.py script is also provided).

#AmazonNovaAct #AmazonBedrock #SyntheticMonitoring #LLM #AWS

---

*Source: [Implementing synthetic monitoring using Amazon Nova Act | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/implementing-synthetic-monitoring-using-amazon-nova-act/)*
