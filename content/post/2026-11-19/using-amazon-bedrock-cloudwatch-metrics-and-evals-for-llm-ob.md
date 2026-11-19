---
title: "Using Amazon Bedrock CloudWatch metrics and evals for LLM observability"
slug: "using-amazon-bedrock-cloudwatch-metrics-and-evals-for-llm-observability"
description: "Airbnb uses Amazon Bedrock to run its internal coding agent tool, AirChat, and has developed a specific observability workflow that combines AWS CloudWatch metrics with custom evaluations. This..."
date: 2026-11-19T06:12:23+05:30
tags: [AmazonBedrock, CloudWatch, LLMObservability, Airbnb, AIEngineering]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "AI Agents", "DevOps"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22452-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Using Amazon Bedrock CloudWatch metrics and evals for LLM observability

Airbnb uses Amazon Bedrock to run its internal coding agent tool, AirChat, and has developed a specific observability workflow that combines AWS CloudWatch metrics with custom evaluations. This approach allows the engineering team to monitor production performance, manage costs, and validate model changes effectively.

## 🔍 Overview
Amazon Bedrock provides access to foundation models from multiple providers through a common API, with AWS managing the underlying infrastructure. At Airbnb, thousands of engineers use AirChat weekly to run coding agents. These agents send model requests through an internal LLM gateway that runs on Amazon Bedrock, ensuring that Airbnb’s code, prompts, and model responses are processed within AWS. The system integrates with standard AWS access controls and monitoring tools.

## ⚙️ Key Details
To manage the impact of frequent model updates, Airbnb utilizes a combination of operational metrics and quality evaluations:

*   **Evaluations (Evals):** Before a new model rollout, the team runs evals on a fixed set of representative tasks to measure the model's score and cost per task.
*   **Production Observability:** After a rollout, observability data is used to compare production usage against eval results. If discrepancies exist, the team investigates the cause.
*   **Cost Per Task:** This is defined as the list-price cost of all tokens an agent uses to finish one task. It serves as a key metric alongside performance scores to determine default model and reasoning effort settings.

### CloudWatch Metrics for Bedrock
Most production problems can be diagnosed using specific signals in the AWS/Bedrock namespace in CloudWatch. The following table outlines the key metrics used to monitor latency, throttling, and cost:

| Category | Metric | Description |
| :--- | :--- | :--- |
| Latency | `InvocationLatency` | Measures time from API call to response. |
| Latency | `TimeToFirstToken` | Time until the first token is generated. |
| Latency | `OutputTokenCount` | Total output tokens generated. |
| Latency | `OTPS` | Output tokens per second (derived metric). |
| Throttling | `InvocationThrottles` | Count of throttled requests. |
| Throttling | `EstimatedTPMQuotaUsage` | Estimated tokens per minute quota consumption, including cache write tokens and output burndown multipliers, across inference APIs. |
| Cost | `InputTokenCount` | Uncached input tokens. |
| Cost | `CacheReadInputTokenCount` | Input tokens read from cache (lower cost than uncached). |
| Cost | `CacheWriteInputTokenCount` | Input tokens written to cache (can have higher cost depending on model). |
| Cost | `OutputTokenCount` | Generated output tokens. |

The `EstimatedTPMQuotaUsage` metric helps teams set proactive alarms, track quota consumption across models, and request quota increases before hitting rate limits. A lower cache hit rate can increase the cost per request due to the pricing differences between uncached input and cache reads.

## 💡 Why It Matters
In a period of about five weeks, eight new models were released. By mid-October, approximately two-thirds of engineer requests through coding agents were directed to these new models. Each release can simultaneously change output tokens, cost, latency, and capacity. Since published benchmark charts do not always reflect how a model handles specific internal workloads, Airbnb’s approach of running evals on their own tasks and monitoring distinct CloudWatch signals allows them to choose appropriate default models and reasoning effort ceilings for their engineers.

#AmazonBedrock #CloudWatch #LLMObservability #Airbnb #AIEngineering

---

*Source: [How Airbnb uses cost per task to operate coding agents on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-airbnb-uses-cost-per-task-to-operate-coding-agents-on-amazon-bedrock/)*
