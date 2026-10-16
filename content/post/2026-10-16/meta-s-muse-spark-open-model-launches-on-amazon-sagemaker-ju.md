---
title: "Meta’s Muse Spark Open model launches on Amazon SageMaker JumpStart"
slug: "metas-muse-spark-open-model-launches-on-amazon-sagemaker-jumpstart"
description: "Muse Spark Open, Meta’s coding‑optimized open‑weight model, is now available in Amazon SageMaker JumpStart, the machine‑learning hub of Amazon SageMaker AI."
date: 2026-10-16T18:01:23+05:30
tags: [Meta, AWS, SageMaker, CodingAI, MoE]
categories: ["AI", "Machine Learning", "AI Agents", "Software Development", "Multimodal AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-22194-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Meta’s Muse Spark Open model launches on Amazon SageMaker JumpStart

Muse Spark Open, Meta’s coding‑optimized open‑weight model, is now available in Amazon SageMaker JumpStart, the machine‑learning hub of Amazon SageMaker AI.

## 🔍 Overview
- Muse Spark Open is a reasoning model built for agentic coding workflows.
- It accepts text, images, documents, audio, and audio‑video as input and returns text.
- The model is released with open weights under the Muse Model License and includes the Muse Spark Usage Policy.

## 🧩 How it works
- Architecture: mixture‑of‑experts (MoE) with **816 billion total parameters**, of which **42 billion are active for each token**.
- Context window: **1 million tokens**, allowing an entire project, its dependencies, and thousands of files to be processed in a single request.
- Agentic behavior: the model plans, acts, observes results, and self‑corrects over long horizons rather than making single tool calls.
- Multimodal reasoning: beyond code, the model can reason across images, documents, audio, and video.

## ⚙️ Key details
- **Model variants**
  | Variant | Weight format | Recommended SageMaker instance |
  |---|---|---|
  | BF16 (Muse‑Spark‑Open‑816B‑A42B) | BF16 | ml.p6-b300.48xlarge |
  | NVFP4 (Muse‑Spark‑Open‑816B‑A42B‑NVFP4) | 4‑bit floating point (NVFP4) | ml.p5e.48xlarge |
- The NVFP4 variant stores weights in NVIDIA’s 4‑bit floating‑point format, using roughly a quarter of the memory of the BF16 weights, making it the first choice when sizing for cost.
- Deployment: you can deploy the model to a SageMaker AI endpoint in your own AWS account in a few steps, without managing serving infrastructure.
- Control and security: the endpoint runs in your account, allowing you to attach it to an Amazon VPC, encrypt storage with an AWS KMS key, enable network isolation, choose instance types and scaling limits, and pin the model version.

## 🚀 Availability
- The model is offered through SageMaker JumpStart with two variants (BF16 and NVFP4).
- You can deploy it using SageMaker Studio and the SageMaker Python SDK, send a first inference request, and then clean up the endpoint.

## 💡 Why it matters
- **Coding assistants over private repositories** – answer questions, refactor, and debug large codebases with the full project in context, while keeping code on your own endpoint.
- **Long‑running coding agents** – agents can plan changes, edit multiple files, run tests in your sandbox, and adjust based on results.
- **Multimodal engineering workflows** – turn screenshots, design documents, or recorded bug reports with audio/video into reproduction plans or draft fixes.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-22194-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-22194-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-22194-3.png)

#Meta #AWS #SageMaker #CodingAI #MoE

---

*Source: [Meta’s Muse Spark Open now available in Amazon SageMaker JumpStart | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/metas-muse-spark-open-now-available-in-amazon-sagemaker-jumpstart/)*
