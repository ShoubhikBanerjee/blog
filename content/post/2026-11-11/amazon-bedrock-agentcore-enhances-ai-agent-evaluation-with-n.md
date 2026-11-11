---
title: "Amazon Bedrock AgentCore enhances AI agent evaluation with new metrics and custom tools"
slug: "amazon-bedrock-agentcore-enhances-ai-agent-evaluation-with-new-metrics-and-custom-tools"
description: "Amazon Bedrock AgentCore has introduced expanded evaluation capabilities for AI agents, combining built-in, third-party, and customizable metrics to assess performance across multiple dimensions...."
date: 2026-11-11T18:02:06+05:30
tags: [AIagents, AmazonBedrock, EvaluationTools, LLM, AutoEval, DeepEval]
categories: ["AI", "AI Agents", "Machine Learning", "Evaluation Metrics", "Developer Tools"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21893-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore enhances AI agent evaluation with new metrics and custom tools

Amazon Bedrock AgentCore has introduced expanded evaluation capabilities for AI agents, combining built-in, third-party, and customizable metrics to assess performance across multiple dimensions. This update provides developers with a comprehensive toolkit to measure agent effectiveness at both granular and conversational levels.

## 🔍 Overview
AgentCore now integrates three evaluator types: AWS-authored built-in evaluators, third-party managed evaluators from DeepEval/AutoEval, and custom derivations. These tools assess agent behaviors through:
- **Trace-level metrics**: Per-turn or per-tool-call analysis
- **Session-level metrics**: Holistic conversation outcomes

## 🧩 How it works
- **Built-in evaluators** (e.g., `Builtin.GoalSuccessRate`, `Builtin.Helpfulness`) are pre-configured by AWS and referenced by ID.
- **Third-party managed evaluators** leverage DeepEval/AutoEval libraries, with AgentCore handling hosting and inference.
- **Custom evaluators** modify existing evaluators' models, prompts, or rubrics while retaining standard usage.

## ⚙️ Key details
The system covers 18+ evaluation dimensions across five categories:

| Category          | Evaluators                                                                 |
|-------------------|----------------------------------------------------------------------------|
| **Task Completion** | `GoalSuccessRate`, `ToolSelectionAccuracy`, `ToolParameterAccuracy`       |
| **Skills**         | `SkillSelectionAccuracy`, `SkillInstructionFollowing`                     |
| **Safety**         | `Harmfulness`, `Stereotyping`, `Security`                                 |
| **Conversation**   | `ConversationCompleteness`, `KnowledgeRetention`, `Possible`              |
| **Trajectory**     | `TrajectoryExactOrderMatch`, `TrajectoryInOrderMatch`, `TrajectoryAnyOrderMatch` |

Additional specialized metrics include `Humor` for consumer agents.

## 💡 Why it matters
- **Reliability**: Built-in evaluators are AWS-benchmarked for common use cases.
- **Flexibility**: Third-party integration allows reuse of existing development metrics in production.
- **Customization**: Developers can create domain-specific evaluators without starting from scratch.
- **Comprehensive coverage**: Metrics span tool accuracy, safety, long-term context retention, and conversational flow.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21893-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21893-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21893-3.png)

#AIagents #AmazonBedrock #EvaluationTools #LLM #AutoEval #DeepEval

---

*Source: [The agent evaluation playbook: Built-in, DeepEval, and AutoEval on Amazon Bedrock AgentCore Evaluations | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/the-agent-evaluation-playbook-built-in-deepeval-and-autoeval-on-agentcore/)*
