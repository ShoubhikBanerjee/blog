---
title: "Amazon SageMaker AI MTRL Enables Multi‑Turn RL Fine‑Tuning of LLMs"
slug: "amazon-sagemaker-ai-mtrl-enables-multiturn-rl-finetuning-of-llms"
description: "Amazon SageMaker AI MTRL lets you fine‑tune large language models with reinforcement learning in multi‑turn interaction settings."
date: 2026-10-02T22:04:29+05:30
tags: [AmazonSageMaker, ReinforcementLearning, LLMFineTuning]
categories: ["AI", "Machine Learning", "AI Agents", "Large Language Models", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21889-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI MTRL Enables Multi‑Turn RL Fine‑Tuning of LLMs

Amazon SageMaker AI MTRL lets you fine‑tune large language models with reinforcement learning in multi‑turn interaction settings.

## 🔍 Overview
- Fine‑tunes LLMs using reinforcement learning in multi‑turn interaction settings.
- Demonstrated by fine‑tuning a Qwen3.6‑27B model (supported in the US West (Oregon) Region `us‑west‑2`) for a search agent.

## 🛠️ How it works
- Frames an agentic task as a sequence of decisions.
- Generates training data through multi‑turn rollouts.
- Optimizes the model with policy‑gradient algorithms.
- Supports algorithms such as Proximal Policy Optimization (PPO), Clipped Important Sampling Policy Optimization (CISPO), and importance‑sampling (IS) losses, paired with group‑based advantage estimators (GRPO, GRPO pass@k, RLOO, and more).
- Uses asynchronous rollout and trajectory collection to run generation and gradient updates in parallel while keeping off‑policy staleness bounded.
- Allows resumable training by splitting long runs across multiple jobs.

## ⚙️ Key features
- **Modular agent‑environment interface** – low‑code integration.
- **Serverless execution** – production‑scale agentic RL at per‑token pricing without provisioning or managing GPU clusters.
- **Asynchronous rollout & trajectory collection** – parallel generation and gradient updates.
- **Native algorithm library** – PPO, CISPO, IS losses with GRPO, GRPO pass@k, RLOO, etc.
- **Resumable training** – continue beyond single‑job time limits.
- **Trajectory and reward observability** – inspect agent actions turn by turn via MLflow managed by Amazon SageMaker AI.
- **Evaluation jobs** – report reward, pass@k, and trajectory metrics before deploying to an Amazon SageMaker AI endpoint or Amazon Bedrock.

## 📊 Training data
| Dataset | Source | Task |
|---------|--------|------|
| FRAMES | HuggingFace | Multi‑hop factoid QA requiring synthesis across multiple Wikipedia articles |
| BRIGHT | HuggingFace | Reasoning‑intensive retrieval across 12 domains, where relevance needs reasoning, not keyword overlap |

## 🤖 Search agent details
- Enterprise search setting with two tools available:
  - **Lexical search (BM25)** – finds exact keyword matches by counting word frequencies.
  - **Vector search** – converts queries and documents into embedding vectors and computes similarities.
- Turn limit imposed to prevent excessively long responses and to encourage efficient search behavior.

## 🚀 Availability
- Amazon SageMaker AI MTRL is available in the US West (Oregon) Region (`us‑west‑2`) for the Qwen3.6‑27B model.

## 💡 Why it matters
- Provides a low‑code, serverless approach to train agentic RL policies at production scale.
- Enables autonomous LLM‑powered agents to use search tools without the need to manage GPU infrastructure.
- Offers built‑in observability and evaluation before deployment to a SageMaker AI endpoint or Amazon Bedrock.

![figure](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/homepage/global-nav/reinvent-register.3822079bac49f139ae46016a9a99c3eed71fad4a.png)

![figure](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/global-nav/aws-library_illustration_innovation_8_1200.07a6484f8eaa3100138cf8b6dce14f1db024db32.jpg)

![figure](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/global-nav/aws-library_illustration_culture_2_1200.77dd122bde9af49ea0c09cdc009c193866f62ad7.jpg)

#AmazonSageMaker #ReinforcementLearning #LLMFineTuning

---

*Source: [Fine-tune a search agent with multi-turn RL on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/fine-tune-a-search-agent-with-multi-turn-rl-on-amazon-sagemaker-ai/)*
