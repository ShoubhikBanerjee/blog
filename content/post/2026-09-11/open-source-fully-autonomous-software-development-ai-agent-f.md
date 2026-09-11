---
title: "Open Source Fully Autonomous Software Development AI Agent for AWS"
slug: "open-source-fully-autonomous-software-development-ai-agent-for-aws"
description: "An update has been released for a fully autonomous software development AI agent. This self-hosted, open-source solution runs on AWS and provides an experience similar to asynchronous coding agents..."
date: 2026-09-11T12:15:38+05:30
tags: [AWS, OpenSource, AIAgents, SoftwareDevelopment, Serverless]
categories: ["AI", "AI Agents", "Software Development", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/8931462?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Open Source Fully Autonomous Software Development AI Agent for AWS

An update has been released for a fully autonomous software development AI agent. This self-hosted, open-source solution runs on AWS and provides an experience similar to asynchronous coding agents such as Google Jules, OpenAI Codex, or Devin.

## 🔍 Overview

The agent automates AI-powered development workflows within its own dedicated development environment. Its capabilities include:

* Autonomous commit creation via GitHub
* Multilingual support beyond English
* Image input and output capabilities
* Ability to work on OSS forked repositories
* MCP support via integration with MCP servers

## ⚙️ Key Details

| Feature | Description |
| :--- | :--- |
| Management Interface | A modern Next.js webapp for real-time monitoring and session management |
| Slack Integration | Ability to call the agent from Slack |
| REST API | RESTful endpoints for programmatic integration |
| Infrastructure | Powered by AWS serverless services |

## 🚀 Availability

Deployment is available via an AWS Sample One-Click Generative AI Solutions option for minimal configuration. The system has no upfront or fixed costs while not in use.

### Technical Requirements
* Node.js (version 22 or higher)
* npm (version 9 or higher)
* AWS CLI
* Docker
* AWS IAM profile with appropriate permissions

### Setup and Configuration
* **Environment:** Users must copy and edit the `.env.local.example` file located in the `cdk/` directory to create a `.env.local` file before deployment.
* **User Management:** A Cognito user can be automatically created during deployment if a specific variable is set, sending a temporary password via email. Otherwise, users can be created manually through the AWS Cognito Management Console.
* **Permissions:** Managed policies, including AWS Managed policy names or full ARNs, can be configured and attached to the worker instance role.

#AWS #OpenSource #AIAgents #SoftwareDevelopment #Serverless

---

*Source: [aws-samples/remote-swe-agents](https://github.com/aws-samples/remote-swe-agents)*
