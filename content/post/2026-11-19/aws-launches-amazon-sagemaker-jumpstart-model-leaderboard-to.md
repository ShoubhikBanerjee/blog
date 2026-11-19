---
title: "AWS Launches Amazon SageMaker JumpStart Model Leaderboard to Simplify Foundation Model Comparisons"
slug: "aws-launches-amazon-sagemaker-jumpstart-model-leaderboard-to-simplify-foundation-model-comparisons"
description: "Amazon has launched the Amazon SageMaker JumpStart Model Leaderboard, a new capability in Amazon SageMaker Studio designed to help developers compare foundation models side by side on quality, speed,..."
date: 2026-11-19T18:06:46+05:30
tags: [AmazonSageMaker, MachineLearning, AWS, GenerativeAI]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22496-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Launches Amazon SageMaker JumpStart Model Leaderboard to Simplify Foundation Model Comparisons

Amazon has launched the Amazon SageMaker JumpStart Model Leaderboard, a new capability in Amazon SageMaker Studio designed to help developers compare foundation models side by side on quality, speed, and cost.

## 🔍 Overview
Comparing open-weight foundation models often requires searching through disparate model cards and benchmark scores published under varying conditions. The Amazon SageMaker JumpStart Model Leaderboard addresses this challenge by providing a central, standardized view directly inside Amazon SageMaker Studio. 

Located on the JumpStart base models page next to the Categories and All models views, the leaderboard uses existing search and filter functions and launches directly into a leaderboard of large language models (LLMs). At launch, the tool covers more than 70 models from providers including Meta, Google, Qwen, IBM, and Arcee, with more models to be added over time.

## 🧩 How it works
For each model, the leaderboard displays two types of information obtained through consistent, unified methods:
* **Quality scores**: AWS runs these scores across three public reasoning benchmarks using a single evaluation harness and setup for all models.
* **Performance and cost metrics**: AWS measures these metrics by sending a standardized test workload to an endpoint configured for each model's deployment setup, revealing how fast a model responds and how much it costs to run.

Because all metrics are gathered from the same evaluation environment, users can perform a like-for-like comparison without relying on inconsistent data from different websites.

## ⚙️ Key details
At launch, the leaderboard reports three separate reasoning benchmarks for LLMs to maintain transparency rather than blending the results into a single number:

| Benchmark | Description |
| :--- | :--- |
| **BIG-Bench Hard (BBH)** | A set of challenging tasks requiring multi-step reasoning, such as logical deduction, tracking objects, and multi-step arithmetic. |
| **GPQA Diamond** | Graduate-level science questions that are difficult to answer by searching the web, offering a good signal of deep reasoning. |
| **MMLU-Pro** | Broad knowledge and reasoning across multiple subjects including science, law, and engineering, utilizing harder multiple-choice questions. |

Users can control which performance and cost numbers they see using two menus above the leaderboard:
* **Use case profile**: Select a profile closest to your workload from the *View benchmarks for your use case* menu (the default is *Max Context*). This profile changes only the performance and cost metrics; the quality scores remain the same.
* **Optimization goal**: Choose the deployment configuration using the *Optimized for* menu (the default is *Balanced*).

The optimization configurations are defined as follows:
* **Balanced**: The configuration with the lowest estimated cost per token, balancing hourly instance price and throughput.
* **Cost optimized**: The configuration with the lowest hourly instance type price. Latency may be higher and throughput lower.
* **Latency optimized**: The configuration optimized for the lowest time to first token (TTFT).
* **Throughput optimized**: The configuration with the highest throughput, which can use speculative decoding.

## 💡 Why it matters
Historically, choosing a starting model involved guessing performance and costs for specific use cases. With the SageMaker JumpStart Model Leaderboard, AWS runs every benchmark using the same evaluation setup. This eliminates the issues associated with published benchmark scores originating from different teams, prompts, or hardware configurations, allowing developers to confidently transition from a shortlist to a deployed model.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22496-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22496-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22496-3-1.png)

#AmazonSageMaker #MachineLearning #AWS #GenerativeAI

---

*Source: [Introducing the Amazon SageMaker JumpStart Model Leaderboard | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-the-amazon-sagemaker-jumpstart-model-leaderboard/)*
*Source: [How Salesforce is advancing global-scale model serving with cross-Region inference routing in Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-salesforce-is-advancing-global-scale-model-serving-with-cross-region-inference-routing-in-amazon-sagemaker-ai/)*
