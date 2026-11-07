---
title: "Taxbit launches Assist, a permission‑aware AI assistant for compliance teams"
slug: "taxbit-launches-assist-a-permissionaware-ai-assistant-for-compliance-teams"
description: "Taxbit, the digital‑asset tax and accounting compliance platform founded in 2018, has added a cited, permission‑aware AI assistant – Taxbit Assist – directly inside its product dashboard. The..."
date: 2026-11-07T18:01:21+05:30
tags: [Taxbit, AIassistants, AmazonBedrock, ComplianceAI]
categories: ["AI", "FinTech", "AI Agents", "Machine Learning", "RegTech"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21532-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Taxbit launches Assist, a permission‑aware AI assistant for compliance teams

Taxbit, the digital‑asset tax and accounting compliance platform founded in 2018, has added a cited, permission‑aware AI assistant – Taxbit Assist – directly inside its product dashboard. The assistant helps compliance teams answer questions without digging through documentation or opening support tickets.

## 🔍 Overview
- Taxbit serves enterprises such as exchanges, payment services, and brokers.
- Assist answers questions in‑context, providing source links and indicating when it does not know an answer.
- More than 55 % of users who ask Assist a question return within 24 hours to ask another, according to internal production analytics.

## 🧩 How it works
1. **User query** – A user types a question in the Taxbit dashboard.
2. **Secure forwarding** – A streaming chat API forwards the query to the AgentCore runtime together with the user’s verified identity (email, organization ID, dashboard roles).
3. **Guardrails & PII masking** – Amazon Bedrock Guardrails screen the message; any personally identifiable information is masked in place. If the message is blocked, the model is never invoked.
4. **Retrieval** – The agent pulls candidate passages from an Amazon Bedrock Knowledge Base (RAG capability backed by Amazon S3 Vectors) and reranks them server‑side.
5. **Reasoning & permission check** – Amazon Bedrock models reason over the passages and verify the user’s feature and role access before recommending any workflow.
6. **Response** – The answer streams back to the dashboard with source links; AgentCore memory preserves context across turns.
7. **Observability** – Each request emits OpenTelemetry traces to Amazon CloudWatch for evaluation tooling.

## ⚙️ Key technical details
- **Agent**: Small Python application (system prompt, model, eight tools).
- **Runtime**: Strands Agents SDK on Amazon Bedrock AgentCore.
- **Deployment**: ARM64 container image stored in Amazon ECR, pulled and scaled on demand.
- **Model access**: Runs a foundation model via Amazon Bedrock, using cross‑Region inference profiles and geography‑aware inference for data residency.
- **Security model**:
  - The model never receives identity information; email, org ID, and roles are bound to tools before the model sees them.
  - The model can decide whether to check permissions but cannot set whose permissions to check.
  - Input is sanitized at the boundary, preventing prompt‑injection attacks.
- **Data access**: The agent has no read access to customer tax data; it answers only from product knowledge and can only create the caller’s own support tickets.
- **Compliance**: Developed and operated in line with ISO/IEC 42001, the international standard for AI management systems.

## 🚀 Availability
Assist is available as an integrated feature inside the Taxbit dashboard for all existing Taxbit customers.

## 💡 Why it matters
- Provides immediate, cited answers, reducing the need for manual documentation searches or support tickets.
- Embeds robust security and privacy safeguards, ensuring identity data never reaches the language model.
- Leverages Amazon Bedrock’s managed RAG, guardrails, and observability stack, demonstrating a production‑grade AI integration for regulated financial workflows.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21532-1.gif)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21532-2.gif)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21532-3.png)

#Taxbit #AIassistants #AmazonBedrock #ComplianceAI

---

*Source: [Taxbit Assist: A grounded, role-aware AI agent on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/taxbit-assist-a-grounded-role-aware-ai-agent-on-amazon-bedrock-agentcore/)*
