---
title: "Self-Hosted Open-Source Fully Autonomous Software Development AI Agent on AWS"
slug: "self-hosted-open-source-fully-autonomous-software-development-ai-agent-on-aws"
description: "A new example implementation of a fully autonomous software development AI agent has been released. This self-hosted, open-source solution runs on AWS and provides an experience similar to..."
date: 2026-09-17T00:45:10+05:30
tags: [AWS, AIagents, OpenSource, SoftwareDevelopment]
categories: ["AI", "AI Agents", "Cloud Computing", "Software Development"]
image: "https://avatars.githubusercontent.com/u/8931462?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Self-Hosted Open-Source Fully Autonomous Software Development AI Agent on AWS

A new example implementation of a fully autonomous software development AI agent has been released. This self-hosted, open-source solution runs on AWS and provides an experience similar to cloud-based asynchronous coding agents such as Google Jules, OpenAI Codex, or Devin.

## 🔍 Overview
The agent automates AI-powered development workflows within its own dedicated development environment. It is designed to operate independently of a user's laptop and can push autonomous commits from a GitHub user.

## ⚙️ Key Details

| Feature | Description |
| :--- | :--- |
| Management Interface | Web-based Next.js app for session management and real-time monitoring |
| Slack Integration | Ability to call the agent from Slack |
| REST API | RESTful endpoints for programmatic integration |
| GitHub Integration | Instructions via GitHub issues; supports single instructions to multiple repos and OSS forked repositories |
| Multimodal Capabilities | Support for input and output of images |
| Language Support | Capability to speak languages other than English |
| MCP Support | Integration with MCP servers |

## 🧩 How it works
The system is powered by AWS serverless services, resulting in minimal maintenance costs and no upfront or fixed costs when the system is not in use.

## 🚀 Availability
Users can utilize a one-click deployment solution via AWS Sample One-Click Generative AI Solutions. Deployment requirements include:

* Node.js (version 22 or higher)
* npm (version 9 or higher)
* AWS CLI
* Docker
* AWS IAM profile with appropriate permissions

During deployment, a Cognito user can be automatically created if a variable is set, with a temporary password sent via email; otherwise, users can be created manually through the AWS Cognito Management Console. Users may also configure additional managed policies for the worker instance role.

#AWS #AIagents #OpenSource #SoftwareDevelopment

---

*Source: [aws-samples/remote-swe-agents](https://github.com/aws-samples/remote-swe-agents)*
