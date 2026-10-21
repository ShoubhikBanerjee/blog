---
title: "Fine-tuning GPT-OSS-20B for Multilingual Reasoning with SFT and GRPO"
slug: "fine-tuning-gpt-oss-20b-for-multilingual-reasoning-with-sft-and-grpo"
description: "We fine‑tuned the open‑weight reasoning model **GPT‑OSS‑20B** to produce chain‑of‑thought and final answers in French, German, Spanish, and Italian rather than defaulting to English."
date: 2026-10-21T22:03:49+05:30
tags: [GPTOSS, MultilingualAI, FineTuning]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21403-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Fine-tuning GPT-OSS-20B for Multilingual Reasoning with SFT and GRPO

We fine‑tuned the open‑weight reasoning model **GPT‑OSS‑20B** to produce chain‑of‑thought and final answers in French, German, Spanish, and Italian rather than defaulting to English.

## 🔍 Overview
- GPT‑OSS‑20B thinks in English out of the box.
- When prompted to reason in another language, it acknowledges the instruction but continues the chain‑of‑thought in English.
- In a 50‑example multilingual test, the base model produced the reasoning language correctly only **22 %** of the time, almost entirely on English examples (English 100 %, French 0 %, German 10 %, Spanish 0 %, Italian 0 %).
- Users expect both the reasoning process and the final answer to appear in the requested language.

## 🧩 How it works
- **Supervised Fine‑Tuning (SFT)** teaches a behavior the model does not have (e.g., multilingual chain‑of‑thought).
- **Group Relative Policy Optimization (GRPO)** refines a behavior the model can already produce occasionally by sampling a group of responses per prompt and pushing the policy toward the above‑average ones.
- If the desired behavior has zero probability in the base distribution, GRPO has little to reinforce, which explains many of the observed results.

## ⚙️ Training Setup
- **Dataset**: `HuggingFaceH4/Multilingual-Thinking` – chain‑of‑thought reasoning translated into EN/FR/DE/ES/IT, ~949 training examples and 50 validation examples.
- **Evaluation**: 50 test cases (10 math/logic problems × 5 languages). Metrics: *Reasoning‑language correct* (chain‑of‑thought in target language) and *Answer‑language correct* (final answer in target language).
- **Fine‑tuning method**: Low‑Rank Adaptation (LoRA) for both SFT and GRPO.
- **Compute**: Amazon SageMaker HyperPod with Amazon EKS orchestration; PyTorch TRL library for GPT‑OSS‑20B runs; veRL trainer with Ray, KubeRay, and vLLM for the Qwen2.5‑7B control experiment.
- **Storage & networking**: Model checkpoints and data on Amazon FSx for Lustre; inter‑node communication via Elastic Fabric Adapter (EFA).
- **Workflow**: User submission lands on the EKS control plane, which schedules a Ray head pod and worker pods that mount FSx for Lustre and run the trainer and rollout workers.

## 📊 Results
- **SFT alone** was sufficient to teach multilingual reasoning where the base model had zero probability (e.g., French, Spanish, Italian). 
- **GRPO added measurable value** only when the base model already produced the behavior some of the time (e.g., German, where baseline was 10 %).
- A parallel experiment with Qwen2.5‑7B across two tasks confirmed that *SFT does most of the work, GRPO refines when there is headroom*, and matching the technique to the capability gap determines the outcome.

## 💡 Takeaways
- Closing the multilingual reasoning gap is primarily a supervised fine‑tuning problem.
- Reinforcement learning with GRPO is useful only when the model’s base distribution assigns non‑zero probability to the desired behavior.
- Parameter‑efficient LoRA fine‑tuning works well on large open‑weight models within the SageMaker HyperPod ecosystem.
- Selecting the right technique based on the specific capability gap yields the most efficient improvements.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21403-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21403-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21403-3.jpg)

#GPTOSS #MultilingualAI #FineTuning

---

*Source: [Fine-tuning GPT-OSS-20B for multilingual reasoning on Amazon SageMaker HyperPod | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/fine-tuning-gpt-oss-20b-for-multilingual-reasoning-on-amazon-sagemaker-hyperpod/)*
