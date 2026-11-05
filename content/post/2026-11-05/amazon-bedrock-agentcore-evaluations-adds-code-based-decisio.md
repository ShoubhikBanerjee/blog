---
title: "Amazon Bedrock AgentCore Evaluations adds code‑based decision model support"
slug: "amazon-bedrock-agentcore-evaluations-adds-codebased-decision-model-support"
description: "Amazon Bedrock AgentCore Evaluations now lets you hook external decision‑model back‑ends through custom code‑based evaluators, enabling calibrated probability scores to be used alongside built‑in LLM..."
date: 2026-11-05T06:03:43+05:30
tags: [AmazonBedrock, AgentCore, DecisionModels, LLMEvaluations]
categories: ["AI", "Machine Learning", "AI Agents", "Evaluation", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22136-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Evaluations adds code‑based decision model support

Amazon Bedrock AgentCore Evaluations now lets you hook external decision‑model back‑ends through custom code‑based evaluators, enabling calibrated probability scores to be used alongside built‑in LLM judges.

## 🔍 Overview
- AgentCore Evaluations scores an agent throughout its lifecycle – on demand, in batch jobs, and against production traffic.
- The service ships with 15 built‑in evaluators that use a general‑purpose LLM to assess responses against a rubric.
- Custom evaluators can be defined as either **LLM‑as‑a‑judge** or **code‑based**.

## 🧩 How it works
- **LLM‑as‑a‑judge evaluators** apply your instructions and rating scale with a model in Amazon Bedrock, producing a score and a rationale.
- **Code‑based evaluators** run your own logic in an AWS Lambda function.  The Lambda can call any external system, model, or API – including a decision model.
- This post demonstrates connecting two decision‑model back‑ends to AgentCore Evaluations via code‑based evaluators.

## ⚙️ Key details
- **Decision model definition** – a small, specialized model that selects from a fixed set of options and returns calibrated confidence scores rather than free‑form text.
- **Advantages** – returns a calibrated probability distribution that can be thresholded, aggregated, and acted on programmatically.
- **Supported question types** (both Jev and Strands Decider):
  - **Noul** – Yes/No question, probability 0 → 1.
  - **Choice** – Up to 255 options, returns most probable option, full distribution, and confidence.
  - **Score** – 2 → 10 ordered levels, returns probability‑weighted score, distribution, and confidence.

### Decision model back‑ends
| Backend | Hosting type |
|---|---|
| Jev (TypeSafe) | Hosted decision model |
| Strands Decider 2B | Open‑source model you run yourself |

## 🚀 Example: HR Assistant evaluation
- An HR Assistant agent is built with **Strands Agents** and deployed to the **AgentCore runtime**.
- The agent answers employee questions using five tools that return fixed mock data (PTO balances, PTO requests, HR policies, benefits, and pay stubs).
- Evaluation combines:
  1. Deterministic code‑based checks.
  2. Built‑in LLM‑as‑a‑judge evaluators.
  3. Decision‑model evaluators backed by Jev or Strands Decider 2B.

## 💡 Why it matters
- General‑purpose LLM evaluators output a score with a rationale, while decision models output a probability distribution over predefined answers.
- The direct confidence measure from decision models enables reliable thresholds and programmatic actions, avoiding the drift observed in free‑form LLM confidence.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22136-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22136-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22136-3.png)

#AmazonBedrock #AgentCore #DecisionModels #LLMEvaluations

---

*Source: [Use decision models with Amazon Bedrock AgentCore Evaluations | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/use-decision-models-with-amazon-bedrock-agentcore-evaluations/)*
