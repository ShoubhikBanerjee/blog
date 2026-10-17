---
title: "AWS adds continuous quality loop to Bedrock AgentCore multi‑agent sales system"
slug: "aws-adds-continuous-quality-loop-to-bedrock-agentcore-multiagent-sales-system"
description: "AWS SMGS Operations team updated its production multi‑agent solution with a continuous quality loop built on Amazon Bedrock AgentCore. The loop monitors answer correctness and traces failures back to..."
date: 2026-10-17T22:02:31+05:30
tags: [AWS, Bedrock, AIAgents, DataQuality]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21894-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS adds continuous quality loop to Bedrock AgentCore multi‑agent sales system

AWS SMGS Operations team updated its production multi‑agent solution with a continuous quality loop built on Amazon Bedrock AgentCore. The loop monitors answer correctness and traces failures back to data, prompts, or code.

## 🔍 Overview
- The system lets sellers and sales leaders ask business questions in plain English from Amazon Quick.
- Answers are scoped to the user’s territory and role‑level security.
- Field teams rely on the answers for account‑strategy planning and customer‑meeting preparation.

## 🧩 How it works
- Amazon Bedrock AgentCore orchestrates several specialized sub‑agents that each own a distinct capability domain.
- Upstream pipelines refresh the underlying data every week.
- Amazon Bedrock Guardrails, CloudWatch, S3, Redshift, Quick, and Lambda provide safety, observability, and persistence.

## ⚙️ Continuous quality loop
- **Monitoring** stays green across runs, but the system only reports that it responded, not whether the answer is correct.
- Errors observed in pre‑production include:
  * Reporting a $410.08 M revenue figure when the source was $410.08.
  * Labeling Sales Revenue as “Sales Revenue excluding Adjustments.”
  * Offering an Annual Recurring Revenue estimate that does not exist in the data.
  * Presenting its own calculations as sourced facts.
- Risk grows with each new agent and any change to data, prompts, code, or models.
- Coordinated releases can create a mismatch window where a data change, tool change, and prompt update land separately; a pre‑production test showed this dropped the pass rate from **78 %** to **38 %**.
- To address these risks, a framework is required that:
  * Shows whether answers are grounded and correct before every release and continuously in production.
  * Traces each failure back to its root cause—data, prompt, or agent code.

## 📊 Impact
- Serves two audiences:
  1. **Field sales teams** – replaces hours of manual analysis with on‑demand conversational intelligence, surfacing risks and opportunities.
  2. **Leadership** – powers Weekly Business Reviews and other cadences without manual report preparation.
- The same agentic system is used both on the front line and at scale for performance review.

## 🗂️ Components
| Sub‑Agent | Capability |
|---|---|
| **Performance Insights Agent** | Generates natural‑language business‑intelligence narratives from complex sales data, scoped to territory. |
| **Customer Insights Agent** | Synthesizes product usage, support history, contract status, and engagement data into a 360° customer view. |
| **Data Insights Agent** | Provides text‑to‑SQL querying of structured analytics data in plain English. |
| **Direct Dashboard Access** | Allows users to view underlying dashboards directly from the conversational interface. |

## 🛠️ Underlying services
- **Amazon Bedrock AgentCore** – core orchestration and evaluation (AgentCore Evaluations). 
- **Amazon Bedrock Guardrails** – safety layer.
- **Amazon CloudWatch** – metrics, alarms, tracing.
- **Amazon S3 & Amazon Redshift** – evaluation persistence.
- **Amazon Quick** – dashboard rendering.
- **AWS Lambda** – custom evaluators.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/AgentCore-Evaluation-Journey.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/Screenshot-2026-10-16-at-3.46.59 PM.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21894-3.png)

#AWS #Bedrock #AIAgents #DataQuality

---

*Source: [Building trust in AI agents: A production-ready evaluation framework with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/building-trust-in-ai-agents-a-production-ready-evaluation-framework-with-amazon-bedrock-agentcore/)*
