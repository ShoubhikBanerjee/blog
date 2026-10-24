---
title: "Amazon SageMaker AI Introduces Multi-Turn Reinforcement Learning for Agents"
slug: "amazon-sagemaker-ai-introduces-multi-turn-reinforcement-learning-for-agents"
description: "Amazon SageMaker AI has introduced Multi-Turn Reinforcement Learning (MTRL), a serverless capability designed to train models on sequences of actions where the only reliable feedback is whether the..."
date: 2026-10-24T18:02:39+05:30
tags: [AmazonSageMaker, ReinforcementLearning, AIAgents, AWS, MachineLearning]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/12/ML-22014-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI Introduces Multi-Turn Reinforcement Learning for Agents

Amazon SageMaker AI has introduced Multi-Turn Reinforcement Learning (MTRL), a serverless capability designed to train models on sequences of actions where the only reliable feedback is whether the entire sequence succeeded.

## 💡 Why it matters
Most fine-tuning focuses on producing a better answer to a single prompt. However, agents performing tasks like triaging support tickets or filing expense reports require a sequence of actions where each step depends on previous outcomes. Traditional supervised fine-tuning lacks labels for these sequences, and single-turn reinforcement learning cannot credit decisions made several steps before an outcome.

## 🧩 How it works
Multi-Turn Reinforcement Learning trains models using the following architecture and process:

* **Infrastructure**: SageMaker AI owns the training job and policy model. It sends prompts through an AWS Lambda forwarder to an agent hosted on Amazon Bedrock AgentCore or other infrastructure such as Amazon EKS, Amazon EC2, or AWS Fargate.
* **Execution**: The agent calls the policy model, acts in the environment for as many turns as needed, and reports a single reward at the end of the episode.
* **Optimization**: Group Relative Policy Optimization (GRPO) updates a Low-Rank Adaptation (LoRA) adapter on the policy model based on the spread of rewards across several rollouts of the same word.
* **Deployment**: A single Python file deployed to AgentCore contains the environment, the tool, and the scoring function.

## ⚙️ Key details
To demonstrate MTRL, a run was conducted using the game Wordle and the GPT-OSS-20B model. Wordle was selected because its rules are few, guesses depend on previous feedback, and outcomes are scored objectively.

| Metric | Result |
| :--- | :--- |
| Model used | GPT-OSS-20B |
| Solve rate (default reasoning) | Increased from 61% to 84% |
| Solve rate (low effort) | Increased from 15% to 69% |
| Training cost | Approximately $339 in training tokens |
| Training duration | 12 hours 40 minutes |
| Total rollouts | 105,486 |

**Training Token Consumption:**
* Prefill: 491.6 million
* Sample: 159.7 million
* Train: 643.3 million

## 🚀 Availability
* **Privacy**: Datasets, agents, and trained models remain in the user's AWS account and are not used to train base models.
* **Code**: All code is available in the accompanying aws-samples repository.
* **Billing**: The AgentCore runtime is billed separately for vCPU and memory usage.

#AmazonSageMaker #ReinforcementLearning #AIAgents #AWS #MachineLearning

---

*Source: [Multi-Turn Reinforcement Learning on Amazon SageMaker AI: A hands-on guide | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/multi-turn-reinforcement-learning-on-amazon-sagemaker-ai-a-hands-on-guide/)*
