---
title: "Serving llama.cpp Decision Models on SageMaker with Text and Structured Paths"
slug: "serving-llama-cpp-decision-models-on-sagemaker-with-text-and-structured-paths"
description: "Deploy decision models with llama.cpp on Amazon SageMaker AI gives you a managed path for serving quantized models on CPU or GPU infrastructure."
date: 2026-10-12T22:04:14+05:30
tags: [SageMaker, llamacpp, SemIf, AIInference, DecisionModels]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Generative AI", "Model Serving"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/09/ML-22079-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Serving llama.cpp Decision Models on SageMaker with Text and Structured Paths

Deploy decision models with llama.cpp on Amazon SageMaker AI gives you a managed path for serving quantized models on CPU or GPU infrastructure.

## 🔍 Overview
- Two deployment paths are available from the same packaged model (Figure 1). 
- **Text‑generation path** uses the AWS Deep Learning Container (DLC) for llama.cpp and returns generated responses through the OpenAI‑compatible chat completions API.
- **Structured‑decision path** builds a child image that replaces the default server with a SemIf adapter and returns probabilities for declared options.

## 🧩 How it Works
### Standard text‑generation path
1. Package the model as `model.tar.gz` in Amazon S3.
2. Reference the published AWS DLC image for llama.cpp directly.
3. At container start, the DLC scans `/opt/ml/model` for the first **.gguf** file.
4. The container maps `POST /invocations` to **llama‑server** at `/v1/chat/completions`.
5. `SM_LLAMA_CPP_*` environment variables are passed as arguments to llama.cpp.

### Structured‑decision path (SemIf)
1. Use AWS CodeBuild to build a **child image** that keeps the DLC’s compiled CPU or CUDA libraries.
2. Replace the default entry point with a SageMaker‑compatible SemIf adapter.
3. Store the child image in Amazon Elastic Container Registry (ECR).
4. The adapter reads the final‑position logits and state that the llama‑server API does not expose, and returns a **decision schema** with `option_ids`, `probabilities`, `option_logits`, plus prompt, timing, and model metadata.

## ⚙️ Key Details
- The AWS DLC for llama.cpp accepts the OpenAI Chat Completions schema.
- Generated text is found in `choices[0].message.content` of the response.
- SemIf uses a constrained decision schema (no chat messages) and returns:
  - `option_ids`
  - `probabilities`
  - `raw option_logits`
  - `prompt`, `timing`, and pinned model metadata.
- Stable option IDs let applications apply thresholds, fallbacks, and policy checks without parsing free‑form text.
- SemIf belongs to a broader class of decision models that score application‑defined outcomes from unstructured state. Other implementations mentioned are Jev, TypeSafe’s decision model, Kev, and Strands Decider 2B.

## 🚀 When to Use Which Path
- **Standard text‑generation** – Use when you need OpenAI‑compatible chat completions via `InvokeEndpoint`.
- **Structured‑decision (SemIf)** – Build a child image only when you need direct access to logits or state, such as:
  - Routing a case to a specific queue
  - Extracting a single value from a known set
  - Assigning incident priority
  - Checking a policy outcome
  - Selecting an agent action
- Keep authorization and deterministic business rules outside the model and validate probabilities before treating them as operational confidence.

## 💡 Why It Matters
- The managed SageMaker AI path removes the need to run custom inference servers for quantized llama.cpp models.
- By swapping in a SemIf adapter, the same model can serve both free‑form text and structured decision outputs, reducing model duplication.
- Applications gain deterministic, audit‑ready probabilities while still leveraging a single underlying LLM.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/09/ML-22079-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2025/07/09/ML-19067-image-19-1.jpeg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/06/16/ML-21172-6.png)

#SageMaker #llama.cpp #SemIf #AIInference #DecisionModels

---

*Source: [Deploy decision models with llama.cpp on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/deploy-decision-models-with-llama-cpp-on-amazon-sagemaker-ai/)*
