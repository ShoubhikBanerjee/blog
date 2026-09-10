---
title: "Introducing the Agent Evaluation Metric for Turn-Level Quality Measurement"
slug: "introducing-the-agent-evaluation-metric-for-turn-level-quality-measurement"
description: "The Agent Evaluation Metric (AEM) has been introduced as a decomposable, turn-level method to measure the quality of AI agents."
date: 2026-09-10T22:04:27+05:30
tags: [AEM, AIAgents, AIEvaluation, LLM]
categories: ["AI", "Machine Learning", "AI Agents", "Software Evaluation"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/03/ML-20819-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Introducing the Agent Evaluation Metric for Turn-Level Quality Measurement

The Agent Evaluation Metric (AEM) has been introduced as a decomposable, turn-level method to measure the quality of AI agents.

## 💡 Why it matters
Existing agent evaluation tools often score quality holistically at the response or task level, which creates several gaps:
* **Task-level metrics**: Goal success rates indicate if a task was completed but do not identify which quality dimension failed.
* **Single-turn metrics**: Evaluations of faithfulness or helpfulness occur in isolation and do not account for how errors propagate across turns.
* **Holistic scores**: These cannot distinguish between a missing required field and a factual error, and they require re-architecting to add new dimensions like safety or instruction retention.
* **Error propagation**: A single incorrect tool call can cascade into downstream failures across multiple turns.

## 🧩 How it works
AEM defines agent quality as a composite indicator built from named, separately measurable sub-metrics. This decompose-evaluate-compose pattern allows the metric to be measured per turn and composed across a trajectory. While this pattern can extend to reasoning depth, safety, and instruction retention, it is first being applied to the dimension of correctness.

## ⚙️ Key details
Correctness is computed per turn, and a turn's correctness is treated as a binary pass or fail. If a turn fails, a specific failure reason names the field and the sub-metric involved.

| Turn Type | Structural Foundation | Completeness Sub-Metric | Truthfulness Sub-Metric |
| :--- | :--- | :--- | :--- |
| **Response Turn** | N/A | Does the reply cover the full query? | Is the free text factually consistent? |
| **Action Turn** | Right tool and action selection | Are all required parameter keys present? | Are the parameter values semantically correct? |

## 🔍 Overview
Correctness is the first dimension instantiated for AEM. It relies on two primary sub-metrics:
* **Truthfulness**: Whether the values produced by the agent are factually consistent with expectations.
* **Completeness**: Whether all required elements are present.

#AEM #AIAgents #AIEvaluation #LLM

---

*Source: [Agent Evaluation Metric for multi-turn conversations | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/agent-evaluation-metric-for-multi-turn-conversations/)*
