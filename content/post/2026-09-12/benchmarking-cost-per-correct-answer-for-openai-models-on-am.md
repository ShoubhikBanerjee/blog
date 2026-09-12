---
title: "Benchmarking Cost Per Correct Answer for OpenAI Models on Amazon Bedrock"
slug: "benchmarking-cost-per-correct-answer-for-openai-models-on-amazon-bedrock"
description: "New results from an open-source benchmarking harness evaluate the practical deployment costs and accuracy of several OpenAI models, comparing those hosted on Amazon Bedrock against those on the..."
date: 2026-09-12T12:03:17+05:30
tags: [OpenAI, AmazonBedrock, LLMbenchmarks, AICosts]
categories: ["AI", "Machine Learning", "Cloud Computing", "AI Agents"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21634-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Benchmarking Cost Per Correct Answer for OpenAI Models on Amazon Bedrock

New results from an open-source benchmarking harness evaluate the practical deployment costs and accuracy of several OpenAI models, comparing those hosted on Amazon Bedrock against those on the OpenAI API.

## 🔍 Overview

The evaluation uses the `openai-on-aws/benchmarks-openai` harness to measure "multipliers" that affect actual costs beyond the sticker price of tokens. These include accuracy, token usage per task, and the number of turns required for agentic workloads. The harness runs a single identical code path via the OpenAI Responses API across all tested models.

## ⚙️ Key details

*   **Evaluated Models:**
    *   Amazon Bedrock: gpt-5.6-luna, gpt-5.6-terra, and gpt-5.6-sol (ran with reasoning disabled).
    *   OpenAI API: gpt-5.4-mini and gpt-5.4-nano (ran at defaults).
*   **Measurement Metrics:**
    *   Single-call accuracy and cost on AIME competition mathematics, GPQA Diamond graduate-level science, and MMLU-Pro.
    *   Multi-turn agent trajectories on live web-research tasks.
    *   Rubric-graded professional deliverables using a gpt-5.5 LLM judge.
*   **Cost Calculation:** The cost of a correct answer is estimated by dividing a model's total spend (including wrong attempts) by its number of correct answers.

## 💡 Why it matters

Capability tiers and token efficiency significantly impact total costs. For example, gpt-5.6-sol solves 75 percent of AIME problems compared to 37 percent for gpt-5.4-mini, while leading in GPQA Diamond (68 percent vs 43 percent) and MMLU-Pro (82 percent vs 59 percent).

Agentic workloads further complicate pricing because the harness uses client-managed history (`store: false`), meaning every turn re-sends the system prompt and conversation context. This causes cumulative billed input to grow approximately quadratically with turn count. Consequently, a model that completes a task in five turns rather than eight can provide savings beyond the simple reduction in turns.

## 🚀 Availability

Following a July 30, 2026 price reduction for models on Amazon Bedrock (luna −80 percent and terra −20 percent), the observed cost per correct AIME answer for gpt-5.6-luna is $0.0021, compared to $0.0139 for gpt-5.4-mini. Across these samples, luna has the lowest observed cost per correct answer, including against gpt-5.4-nano.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21634-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21634-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21634-3.png)

#OpenAI #AmazonBedrock #LLMbenchmarks #AICosts

---

*Source: [Beyond the price per token: Choosing the right OpenAI model on Amazon Bedrock for your workload | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/beyond-the-price-per-token-choosing-the-right-openai-model-on-amazon-bedrock-for-your-workload/)*
