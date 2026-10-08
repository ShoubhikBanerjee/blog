---
title: "Anthropic launches Claude Haiku 5.5 on AWS Bedrock and introduces Strands Box sandbox"
slug: "anthropic-launches-claude-haiku-5-5-on-aws-bedrock-and-introduces-strands-box-sandbox"
description: "Today, Anthropic announced that Claude Haiku 5.5 is now available on Amazon Bedrock and through Claude Platform on AWS."
date: 2026-10-08T06:07:34+05:30
tags: [Anthropic, ClaudeHaiku, AWS, AIagents, Sandbox]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Cloud Computing", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-22086-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic launches Claude Haiku 5.5 on AWS Bedrock and introduces Strands Box sandbox

Today, Anthropic announced that Claude Haiku 5.5 is now available on Amazon Bedrock and through Claude Platform on AWS.

## 🔍 Overview
Claude Haiku 5.5 is the fastest and most efficient model in the Claude 5.5 family, built for subagents and high‑volume, cost‑sensitive work. It pairs with the recently announced Claude Opus 5.5 to form a two‑model team: Opus plans and makes judgment calls, while Haiku executes well‑defined tasks quickly and at scale. At the same time, Anthropic launched **Strands Box** in developer preview – an open‑source sandbox that adds OS‑level isolation plus fine‑grained policy control for AI agents.

## ⚙️ How it works
- **Claude Haiku 5.5** acts as a subagent that can route requests, review code, classify long documents, pull key information from small‑to‑medium files, and handle traditional NLP tasks such as classification, summarization, and text generation. It also supports high‑resolution images, multi‑step tool use, and repetitive browser/desktop automation.
- **Effort controls** let developers tune cost against intelligence per task instead of a single setting for an entire workload.
- **Claude Opus 5.5** breaks down complex problems, decides the approach, and performs the hardest reasoning (e.g., release debugging, security review of large pull requests, long analyses).
- **Strands Box** provides two layers of protection:
  * **Containment** – OS‑level isolation (e.g., macOS Seatbelt) defines what files, network endpoints, and tools an agent can reach.
  * **Policy** – Dogwood policy language evaluates actions at multiple enforcement points (network egress, Python interpreter, Shell interpreter, MCP broker). Policies can reference an agent’s history, enabling rules such as “allow a post no more than three times every 10 minutes” or “after reading a file from `customer-data`, block further outbound HTTP requests.”

## 📊 Key details
- **Performance & cost**
  * Faster than other Claude 5.5 models.
  * Costs about **75 % less** than Claude Haiku 4.5 for most tasks.
- **Use‑case spectrum**
  * Coding subagent: routes requests, reviews code, classifies long documents.
  * Knowledge work: scans documents, extracts key information, answers quick questions.
  * Interactive apps: provides rapid answers for simple conversations.
  * High‑volume NLP: classification, summarization, text generation at production scale.
- **Strands Box capabilities**
  * Combines OS isolation with Dogwood policy engine.
  * Enforces decisions for file reads/writes, HTTP methods/paths, and tool invocations.
  * Includes embedded interpreters for Shell and Python (Strands Shell and Monty).
  * Uses an egress gateway proxy and shared event history to write cross‑tool rules.

| Model | Primary Role |
|-------|--------------|
| Claude Opus 5.5 | Plans work, makes judgment calls, handles complex reasoning |
| Claude Haiku 5.5 | Executes fast, high‑volume sub‑tasks (routing, classification, rewriting, etc.) |

## 🚀 Availability
- **Amazon Bedrock**: Haiku 5.5 is available in US, EU, AU, JP, and Global inference profiles, as well as in AWS GovCloud (US) on both `bedrock-runtime` and `bedrock-mantle` endpoints.
- **Data residency**: Keeps data within AWS infrastructure with regional residency.
- **Integration**: Works with existing AWS controls – IAM for access, CloudTrail for audit, CloudWatch for monitoring, and Bedrock Guardrails. Usage appears on your AWS bill.
- **Claude Platform on AWS**: Direct access through the AWS Management Console in North America, offering the same APIs, features, and console experience as Anthropic’s native platform, unified with AWS billing and authentication.
- **Getting started**: Open the Amazon Bedrock console, choose *Test → Playground*, and select Haiku 5.5 as the model.

## 💡 Why it matters
- The cost and speed improvements make it feasible to run many Haiku subagents in parallel, enabling large‑scale agentic workflows.
- Pairing Haiku 5.5 with Opus 5.5 creates a clear division of labor between planning/reasoning and fast execution.
- Strands Box addresses the biggest risk of autonomous agents—unrestricted actions—by combining containment with policy that can enforce contextual limits across tools and over time.
- Unified billing, authentication, and monitoring through AWS simplify operational management for enterprises deploying AI agents at scale.

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/10/06/box-core-diagram.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/Screenshot-2026-10-07-at-1.27.14 PM.png)

#Anthropic #ClaudeHaiku #AWS #AIagents #Sandbox

---

*Source: [Introducing Claude Haiku 5.5 on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-claude-haiku-5-5-on-aws/)*
*Source: [Introducing Strands Box: AI agent sandboxes powered by Dogwood | Amazon Web Services](https://aws.amazon.com/blogs/opensource/introducing-strands-box-ai-agent-sandboxes-powered-by-dogwood/)*
