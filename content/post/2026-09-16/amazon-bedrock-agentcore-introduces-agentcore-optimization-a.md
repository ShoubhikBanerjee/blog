---
title: "Amazon Bedrock AgentCore Introduces AgentCore Optimization and Reflector Agents"
slug: "amazon-bedrock-agentcore-introduces-agentcore-optimization-and-reflector-agents"
description: "Amazon Bedrock AgentCore has introduced AgentCore optimization, a capability designed to help improve the quality of agents through the use of production traces and automated configuration changes."
date: 2026-09-17T00:50:10+05:30
tags: [AmazonBedrock, AgentCore, AIAgents, LLMOps]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21426-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Introduces AgentCore Optimization and Reflector Agents

Amazon Bedrock AgentCore has introduced AgentCore optimization, a capability designed to help improve the quality of agents through the use of production traces and automated configuration changes.

## 🔍 Overview
AgentCore optimization allows users to propose configuration changes using production traces. These changes can be validated via online A/B testing on live traffic and offline batch evaluation before promoting the winners. This process is supported by AgentCore Observability, which provides visibility into agent behavior and signals regarding agent quality.

## 🧩 How it works
The system prompt optimizer utilizes agent traces from AgentCore Observability and a reward signal to produce improved system prompts. This process is managed by an agentic reflector, which performs the following steps:

*   **Analysis:** Reviews evaluated agent behavior to identify patterns distinguishing successful runs from failures.
*   **Proposal:** Proposes targeted changes to the agent configuration, primarily outputting a revised system prompt and an explanation for the changes.
*   **Execution:** The reflector is given a shell tool and access to a directory of traces scored by an evaluator. It can use commands such as `grep`, `cat`, and `diff` to list files, search, read traces, and compare outputs.
*   **Validation:** Before any proposal is applied, it must pass through platform-level guardrails.

## ⚙️ Key details
AgentCore optimization employs different types of reflector agents to drive system prompt recommendations:

| Reflector Type | Description |
| :--- | :--- |
| Single Agent Reflector | Works through the full trace set in a single pass during each optimization epoch. |
| Sub-Agent Reflector | Uses a swarm of agents to dynamically explore different parts of the trace set, trading efficiency for a higher quality ceiling. |

Sub-agents in the Sub-Agent Reflector perform a three-level analysis on single traces:
*   **Surface:** Extracts the reward, difficulty, and outcome.
*   **Turn level:** Uses shell commands like `jq` and `grep` to parse rollout JSON and locate the decision point where the trajectory diverged from the optimal path.
*   **Cognitive:** Diagnoses the reason for failure at that decision point and provides reflective guidance.

An orchestrator then aggregates these findings, removes duplicates, generalizes recurring patterns, and condenses insights into configuration changes.

## 🚀 Availability
The Sub-Agent Reflector has been launched as an experimental feature in a preliminary release within the Strands open-source GitHub repository.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/16/single-agent-reflector-800w.png)

#AmazonBedrock #AgentCore #AIAgents #LLMOps

---

*Source: [Optimizing agent system prompts with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/optimizing-agent-system-prompts-with-amazon-bedrock-agentcore/)*
