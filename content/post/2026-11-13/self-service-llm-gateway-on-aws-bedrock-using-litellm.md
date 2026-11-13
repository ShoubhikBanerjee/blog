---
title: "Self‑Service LLM Gateway on AWS Bedrock Using LiteLLM"
slug: "selfservice-llm-gateway-on-aws-bedrock-using-litellm"
description: "A new self‑service LLM gateway abstracts Amazon Bedrock behind an OpenAI‑compatible API by running LiteLLM on AWS Fargate. The pattern provides a centrally managed access point for coding assistants..."
date: 2026-11-13T18:03:26+05:30
tags: [LLM, AWS, LiteLLM, Bedrock, AIInfrastructure]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Machine Learning", "DevOps"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-20816-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Self‑Service LLM Gateway on AWS Bedrock Using LiteLLM

A new self‑service LLM gateway abstracts Amazon Bedrock behind an OpenAI‑compatible API by running LiteLLM on AWS Fargate. The pattern provides a centrally managed access point for coding assistants and other developers.

## 🔍 Overview
- An LLM gateway offers a single, centrally managed entry point to foundation models.
- Developers reach the gateway through a single API key, gaining per‑user cost controls and model performance observability.
- The post demonstrates the pattern with Claude Sonnet and Claude Haiku models.

## 🧩 How it works
- **Entry point**: OpenAI‑compatible client → Amazon Route 53 → Amazon CloudFront → Application Load Balancer (ALB).
- **Authentication**: Per‑user API key validated by LiteLLM running on Fargate.
- **State storage**: Amazon RDS (PostgreSQL) holds virtual‑key and spend state; a separate RDS instance stores persistent API‑key metadata and spend tracking.
- **Caching & secrets**: Amazon ElastiCache for Valkey provides non‑persistent response caching; AWS Secrets Manager stores secrets.
- **Model invocation**: LiteLLM invokes Amazon Bedrock Application Inference Profiles using a scoped IAM task role; each model has its own profile managed with AWS CDK.
- **Observability**: Amazon CloudWatch captures requests‑per‑minute (RPM) and tokens‑per‑minute (TPM) metrics and triggers quota alarms; Langfuse adds prompt‑level telemetry and latency tracking.
- **Scaling**: LiteLLM runs in an AWS Fargate task with target‑tracking auto‑scaling on CPU utilization.
- **Admin portal**: A lightweight web portal (integrates with corporate SSO) lets ops engineers set spend policies and developers self‑provision API keys within those limits. The portal also coordinates rate‑limiting across Fargate tasks.

| Model | Inference Profile Management |
|-------|------------------------------|
| Claude Sonnet | Managed with AWS CDK |
| Claude Haiku | Managed with AWS CDK |

## ⚙️ Key details
- OpenAI‑compatible proxy exposed by LiteLLM.
- Per‑user API keys and spend limits enforce cost control.
- Per‑model quota isolation via separate inference profiles.
- Rate‑limiting and non‑persistent caching handled by Valkey.
- CloudWatch metrics (RPM, TPM) plus Langfuse application‑level insights.
- Developers can configure tools such as Claude Code, Continue, and Cursor with a single base URL and API key.

## 🚀 Availability
- The LiteLLM AI Gateway component is open source and suitable for small pilots (free for up to five users).
- A license is required for more than five users.
- LiteLLM Enterprise provides a production‑ready version with SSO, audit logs, delegated admin roles, and support; it also enables the self‑service key issuance described.

## 💡 Why it matters
- Centralizes access to multiple foundation models, simplifying integration for development teams.
- Provides granular cost and usage controls per developer.
- Combines infrastructure‑level metrics with application‑level observability for easier debugging and performance tuning.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-20816-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/20816-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-20816-3.jpg)

#LLM #AWS #LiteLLM #Bedrock #AIInfrastructure

---

*Source: [Building a self-service LLM gateway with Amazon Bedrock and LiteLLM | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/building-a-self-service-llm-gateway-with-amazon-bedrock-and-litellm/)*
