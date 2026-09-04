---
title: "Intuit Deploys EWOK Agent, an AI‑Powered Disaster Recovery Tool Built on Amazon Bedrock"
description: "Intuit has released EWOK Agent, an AI‑powered disaster‑recovery assistant that runs on Amazon Bedrock and extends the existing EWOK system."
date: 2026-09-04T22:05:53+05:30
tags: [Intuit, AmazonBedrock, DisasterRecovery, AIagents]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21646-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Intuit Deploys EWOK Agent, an AI‑Powered Disaster Recovery Tool Built on Amazon Bedrock

Intuit has released EWOK Agent, an AI‑powered disaster‑recovery assistant that runs on Amazon Bedrock and extends the existing EWOK system.

## 🔍 Overview
- Supports products that millions rely on: TurboTax, QuickBooks, Mailchimp, and Credit Karma.
- Extends the **Ecosystem Wide Orchestrator Kit (EWOK)**, Intuit’s centralized internal disaster‑recovery system.
- Delivered as a plug‑in that engineers can install and invoke from Intuit’s Engineering portal or any IDE.

## ⚙️ Existing EWOK Platform
- **Standardizes failover execution** across compute, databases, networking, caches, and asynchronous workloads.
- Service owners declare recovery intent in **YAML**; EWOK orchestrates the underlying infrastructure actions.
- Reduced recovery time from **several hours to ~20 minutes** for supported workloads.
- Prior to EWOK Agent, choosing the correct workflow and handling mid‑recovery exceptions relied on tribal knowledge of experienced on‑call engineers.
- Failover requests during tightly‑restricted deployment windows (e.g., tax season) were rejected unless the engineer followed a detailed emergency‑override procedure.

## 🤖 EWOK Agent – AI‑Powered Extension
- Built with **Amazon Bedrock**, leveraging hundreds of foundation models through a single API.
- Teams across Intuit have used the agent to run failovers for the **past eight months**.
- **Model flexibility:** Ability to evaluate and select the right model for failover reasoning and switch models later without re‑architecting the agent.
- **Security & privacy:**
  - Built‑in Amazon Bedrock Guardrails.
  - Data is **not used to train models** and remains encrypted in transit and at rest.
- Because Amazon Bedrock is fully managed, the reasoning layer was added **without provisioning or managing model infrastructure**.

## 🧩 Architecture & Design Principles
| Component | Role |
|----------|------|
| EWOK (internal) | Deterministic executor of failover actions |
| EWOK Agent | Bounded agentic loop that queries foundation models |
| Amazon Bedrock layer | Thin integration that maps model output (skills) to EWOK commands |

- **Failover knowledge is encoded as typed skills**; the model decides *what* to do, EWOK executes *how*.
- The boundary between model reasoning and deterministic execution is kept crisp to ensure auditability and reliability.
- The pattern (typed skills + thin Bedrock layer + deterministic executor) is **not specific to EWOK** and can be applied to other systems exposing authenticated, auditable APIs.

## 🚀 Benefits
- **Speed:** Recovery times reduced to about 20 minutes.
- **Consistency:** Eliminates reliance on tribal knowledge for workflow selection and exception handling.
- **Flexibility:** Ability to swap foundation models as needs evolve.
- **Security:** Guardrails, encryption, and no model‑training data leakage.
- **Ease of adoption:** Engineers install the plug‑in and run failovers directly from familiar tools.

## 💡 Why It Matters
- Provides a **scalable, AI‑assisted** approach to disaster recovery for services that power millions of users.
- Demonstrates a reusable pattern for coupling foundation‑model reasoning with deterministic internal systems.
- Enhances service availability during critical business periods, such as tax season, by reducing manual overhead and error‑prone processes.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21646-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21646-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21646-3.jpg)

#Intuit #AmazonBedrock #DisasterRecovery #AIagents

---

*Source: [How Intuit built an agentic disaster recovery assistant with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-intuit-built-an-agentic-disaster-recovery-assistant-with-amazon-bedrock/)*
