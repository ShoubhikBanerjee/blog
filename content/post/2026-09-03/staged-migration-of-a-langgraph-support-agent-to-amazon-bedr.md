---
title: "Staged migration of a LangGraph support agent to Amazon Bedrock AgentCore"
description: "A LangGraph customer‑support agent was moved from a notebook prototype to a production‑ready deployment using a four‑stage migration onto Amazon Bedrock services. The walk‑through shows how..."
date: 2026-09-03T22:06:46+05:30
tags: [AWS, Bedrock, AIagents, LangGraph]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-20753-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Staged migration of a LangGraph support agent to Amazon Bedrock AgentCore

A LangGraph customer‑support agent was moved from a notebook prototype to a production‑ready deployment using a four‑stage migration onto Amazon Bedrock services. The walk‑through shows how operational burdens are reduced and how managed runtime, guardrails, and observability are added at each stage.

## 🔍 Overview
- The agent classifies each incoming message, escalates angry customers, and answers everyone else with three tools.
- Model calls already go to Amazon Bedrock.
- It runs on compute you provision, patch and scale.

## ⚙️ Operational burdens (four of ten)
- An agent that works in a notebook isn’t an agent in production.
- After real users arrive, you own work that has nothing to do with your agent’s reasoning.
- Keep one user’s session out of another’s, and hold state across turns and days.
- Auth for every tool the agent calls sits in your code, and the operating system underneath needs patching.

## 🚀 Migration stages
| Stage | Change introduced | What stays the same |
|------|-------------------|--------------------|
| 0 | Model calls go to OpenAI or Anthropic directly; one constructor change. | The agent graph remains unchanged. |
| 1 | Transition onto Amazon Bedrock AgentCore Runtime, Gateway and Memory; graph unchanged. | You own the container, web server, and conversation state. |
| 2 | Rebuild the loop as model‑driven planning on Strands Agents; how it plans moves. | Runtime proved in earlier stage is reused. |
| 3 | Hand the loop to an AgentCore harness (AgentCore capability); dependency updates move here. | Guardrails and managed tools continue to apply. |

- Stopping after stage 1 gives a hosted agent with managed tools and durable state.
- Inference is the one call a migration doesn’t touch, so being on Amazon Bedrock already isn’t a head‑start.

## 🛡️ Guardrails & security
- When the agent reaches production, add Amazon Bedrock Guardrails to filter harmful content, validate grounding against source documents, and block prompt‑injection attempts.
- Those controls apply to any agent regardless of which stage you stop at.
- Gateway takes tool auth and calls your function with its own execution role.
- The agent signs Gateway calls with its own IAM credentials using Signature Version 4; Gateway then invokes the AWS Lambda target under its own execution role.
- Identity brokers credentials and refreshes OAuth tokens for APIs the agent calls on someone’s behalf.
- AWS IAM policies, VPC configuration, WAF rules, and secrets rotation stay yours at every stage.

## 🖥️ Runtime features
- Runtime takes the compute, so OS patching, auto‑scaling, and session isolation stop being yours.
- By default it runs on AWS‑managed infrastructure; you can attach it to a VPC you own.
- Checkpoint storage goes to Memory, which holds conversation state across turns, processes and days.
- Observability sends Runtime logs, metrics and traces to Amazon CloudWatch without you configuring it.

## 📦 Requirements
- An AWS account with Amazon Bedrock model access enabled.
- Python 3.12.
- AWS CLI configured with credentials that can create AgentCore, Lambda, Amazon S3, and IAM resources.

## 📈 Why it matters
- The staged approach isolates the ten operational burdens and lets you adopt managed services incrementally.
- Production‑ready guardrails and built‑in observability reduce the operational load of running an AI‑driven support agent.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-20753-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-20753-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-20753-3.png)

#AWS #Bedrock #AIagents #LangGraph

---

*Source: [Migrate agentic workloads to Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/migrate-agentic-workloads-to-amazon-bedrock-agentcore/)*
