---
title: "Amazon Bedrock adds Sub‑Agent Reflector to AgentCore optimization workflow"
slug: "amazon-bedrock-adds-subagent-reflector-to-agentcore-optimization-workflow"
description: "Amazon Bedrock has released an update to its AgentCore optimization feature, adding an experimental Sub‑Agent Reflector and expanding the system‑prompt optimizer workflow."
date: 2026-09-16T22:05:42+05:30
tags: [AmazonBedrock, AgentCore, AIOptimization, PromptEngineering]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Software Engineering"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21426-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock adds Sub‑Agent Reflector to AgentCore optimization workflow

Amazon Bedrock has released an update to its AgentCore optimization feature, adding an experimental Sub‑Agent Reflector and expanding the system‑prompt optimizer workflow.

## 🔍 Overview
- AgentCore optimization is a capability of Amazon Bedrock AgentCore that helps improve the quality of agents.
- It uses production traces to propose configuration changes, validates them through offline batch evaluation and online A/B testing on live traffic, and promotes the winners.
- AgentCore Observability provides visibility into agent behavior, and evaluations provide signals about agent quality.

## 🧩 How it works
- The system‑prompt optimizer runs inside an **agentic reflector**, the reasoning component of the optimizer.
- The reflector receives the complete trace corpus via a filesystem and can list, search, read, and diff files to examine patterns of success and failure.
- An evaluator scores a collection of traces and writes the scores to a directory accessible to the reflector.
- The reflector proposes updates to the agent configuration, explains why the changes should improve quality, and presents the recommendation for review before any A/B test.
- Proposals must pass platform‑level guardrails before they can be applied.
- Each optimization epoch repeats the cycle: score the traces, reflect, and accept edits that pass the guardrails. Additional epochs can be run to trade optimization time for further quality gains.

## ⚙️ Key details
| Reflector | Role | Notable attributes |
|-----------|------|--------------------|
| Single Agent Reflector | Drives system‑prompt recommendations in AgentCore optimization today | Works through the full trace set in a single pass; repeats epochs of score‑reflect‑apply |
| Sub‑Agent Reflector | Extends the Single Agent Reflector | Uses a swarm of agents to explore different parts of the trace set dynamically; each sub‑agent performs three‑level analysis (Surface, Turn, Cognitive); orchestrator aggregates findings, removes duplicates, and condenses insights into configuration changes |

- Recommendations compare an existing system prompt with a revised version and explain the trace patterns that motivated the changes.
- The recommendation interface provides an explanation of the proposed changes so reviewers can understand the reasoning before testing.
- The Sub‑Agent Reflector trades some efficiency for a higher quality ceiling by focusing each sub‑agent on a single trace without cross‑influence.

## 🚀 Availability
- The Sub‑Agent Reflector has been launched as a preliminary release in the **Strands** open‑source GitHub repository.

## 💡 Why it matters
- Provides an end‑to‑end, trace‑driven workflow for improving agent prompts and configurations.
- Combines offline evaluation, online A/B testing, and guard‑rail validation to ensure only quality‑improving changes are promoted.
- Enables developers to iterate faster by automating the discovery of prompt improvements and offering clear explanations for each recommendation.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/16/single-agent-reflector-800w.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21426-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21426-5.png)

#AmazonBedrock #AgentCore #AIOptimization #PromptEngineering

---

*Source: [Optimizing agent system prompts with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/optimizing-agent-system-prompts-with-amazon-bedrock-agentcore/)*
