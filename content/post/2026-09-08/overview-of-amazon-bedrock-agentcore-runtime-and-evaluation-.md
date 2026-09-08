---
title: "Overview of Amazon Bedrock AgentCore Runtime and Evaluation Capabilities"
description: "Amazon Bedrock AgentCore provides a managed environment for developing, hosting, and evaluating AI agents throughout their lifecycle. The platform integrates agent runtime, observability, and..."
date: 2026-09-08T22:06:20+05:30
tags: [AmazonBedrock, AgentCore, AIAgents, LLM, OpenTelemetry]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-20711-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Overview of Amazon Bedrock AgentCore Runtime and Evaluation Capabilities

Amazon Bedrock AgentCore provides a managed environment for developing, hosting, and evaluating AI agents throughout their lifecycle. The platform integrates agent runtime, observability, and evaluation features to support development workflows.

## 🧩 How it works
AgentCore runtime acts as a managed hosting platform that handles scaling, infrastructure, and session isolation for agent code written in Python or other frameworks. Agents can connect to MCP (Model Context Protocol) servers, which provide a standardized interface for discovering and calling external tools. The development lifecycle is supported by GitHub Actions, which uses OIDC federation to assume AWS IAM roles without requiring long-lived credentials.

## ⚙️ Key details
AgentCore Evaluations functions as the platform's quality measurement layer. It operates by scoring agent interactions using LLM-as-a-judge or code-based evaluation via AWS Lambda, utilizing OpenTelemetry traces captured by AgentCore Observability.

Evaluation methods include:
* On-demand: Evaluates specific sessions by providing span data directly in the API call.
* Online: Monitors production traffic continuously with configurable sampling rates, feeding results into CloudWatch.
* Batch: Scores multiple sessions asynchronously by pointing to CloudWatch Logs.

## 🔍 Built-in Evaluators
The platform includes pre-built evaluators to measure agent performance across several quality dimensions:

| Evaluator | Scope |
| :--- | :--- |
| Helpfulness | Session/Trace/Tool-call |
| Correctness | Session/Trace/Tool-call |
| GoalSuccessRate | Session/Trace/Tool-call |
| ToolSelectionAccuracy | Session/Trace/Tool-call |
| ToolParameterAccuracy | Session/Trace/Tool-call |
| TrajectoryExactOrderMatch | Tool-call sequence |
| TrajectoryInOrderMatch | Tool-call sequence |
| TrajectoryAnyOrderMatch | Tool-call sequence |

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-20711-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-20711-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-20711-3.png)

#AmazonBedrock #AgentCore #AIAgents #LLM #OpenTelemetry

---

*Source: [Automated agent evaluation with Amazon Bedrock AgentCore and GitHub Actions | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/automated-agent-evaluation-with-amazon-bedrock-agentcore-and-github-actions/)*
