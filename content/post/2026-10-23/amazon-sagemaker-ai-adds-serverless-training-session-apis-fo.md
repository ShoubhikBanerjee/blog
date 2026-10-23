---
title: "Amazon SageMaker AI adds serverless training session APIs for custom model fine‑tuning"
slug: "amazon-sagemaker-ai-adds-serverless-training-session-apis-for-custom-model-finetuning"
description: "Amazon SageMaker AI has expanded its serverless model‑customization offering with the general‑availability launch of **training sessions**. The new APIs let customers write and coordinate their own..."
date: 2026-10-23T18:02:55+05:30
tags: [SageMaker, ModelCustomization, ServerlessAI, ReinforcementLearning]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Large Language Models", "Reinforcement Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21950-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI adds serverless training session APIs for custom model fine‑tuning

## 🔍 Overview
Amazon SageMaker AI has expanded its serverless model‑customization offering with the general‑availability launch of **training sessions**. The new APIs let customers write and coordinate their own post‑training logic—such as custom loss functions or reward signals—while SageMaker AI handles all GPU infrastructure, fault recovery, and checkpoint storage.

## 🧩 How it works
Training sessions expose low‑level operations (e.g., `forward_backward()`, `optim_step()`, `sample()`) as SageMaker API calls. Users write the training loop in their own Python process; each call is executed on a live, stateful GPU‑backed session. The service takes care of:
- GPU allocation and distributed execution
- Gradient synchronization and checkpoint storage
- Fault recovery, tenant isolation, and scaling
- Security configuration via IAM roles, optional KMS keys, and VPC settings

Your data, checkpoints, and any custom weights stay in your Amazon S3 bucket in the region you choose, and SageMaker does not reuse them to train other models.

## ⚙️ Key Features
- **No instance‑type or cluster management** – the service automatically provisions serverless GPUs.
- **Fine‑grained algorithmic control** – write custom loss, reward, or preference functions.
- **Multi‑turn reinforcement learning** – managed, serverless support for agents that require several interaction rounds.
- **Flexible adaptation** – choose Low‑Rank Adaptation (LoRA) or full fine‑tuning, and chain techniques through continuous customization.
- **Pay‑per‑token** pricing model.
- **Secure execution** – IAM execution role, optional KMS key, VPC configuration, data stays in your S3 bucket.
- **Evaluation before deployment** – built‑in steps for accuracy, bias, and safety checks.

## 📚 Programming Model
Training sessions are accessed through three SageMaker Python SDK clients:
1. **ServiceClient** – sets platform‑level settings (execution role, model package, S3 output location, optional KMS/VPC) and starts a session.
2. **TrainingClient** – provides operations such as `forward()`, `forward_backward()`, `optim_step()`, and checkpoint handling.
3. **SamplingClient** – handles `sample()` and `compute_logprobs()` for generation and scoring during roll‑outs.

Each API call maps to a single step in your loop. An active session also exposes an OpenAI‑compatible chat completions endpoint, enabling existing client code to sample from the customized model.

## 🚀 Availability
The training‑session APIs are now generally available as part of SageMaker AI serverless model customization. A companion *training sessions cookbook* provides ready‑to‑run SFT and RL recipes.

## 💡 Why it matters
Customizing an open‑weight model with post‑training techniques such as reinforcement learning or preference optimization yields more accurate results for a specific business context (e.g., product catalogs, clinical vocabularies) and reduces inference cost. The new serverless APIs remove the operational burden of managing GPU clusters, allowing teams to focus on algorithmic innovation while still retaining full control over the training procedure.

### Techniques supported
| Technique | What it enables |
|-----------|-----------------|
| SFT (Supervised Fine‑Tuning) | Custom loss or data curriculum |
| DPO (Direct Preference Optimization) | Preference‑based alignment |
| RLVR | Reinforcement‑learning variant |
| RLAIF (RL from AI Feedback) | Feedback‑driven RL |
| Multi‑turn RL | Agent training requiring several interaction rounds |
| LoRA (Low‑Rank Adaptation) | Update a subset of model weights |
| Full fine‑tuning | Update the entire model |

### Real‑world usage examples
- A healthcare claim‑denial triage model built with training sessions validated the platform from day one.
- Fine‑tuning `gpt‑oss‑20b` for agentic multi‑turn tool calling against an Amazon Neptune knowledge graph succeeded with no manual GPU tuning, out‑of‑memory issues, or checkpoint‑resume problems.
- The cookbook demonstrates reinforcement learning on competitive‑programming problems where generated code is scored against unit tests.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/training-sessions-image.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21950-3.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21950-4.jpg)

#SageMaker #ModelCustomization #ServerlessAI #ReinforcementLearning

---

*Source: [Announcing new ways to customize models with SageMaker AI, without managing GPUs | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/announcing-new-ways-to-customize-models-with-sagemaker-ai-without-managing-gpus/)*
*Source: [Write your own training loop — without managing GPUs — with Amazon SageMaker training session APIs | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/write-your-own-training-loop-without-managing-gpus-with-amazon-sagemaker-training-sessions/)*
