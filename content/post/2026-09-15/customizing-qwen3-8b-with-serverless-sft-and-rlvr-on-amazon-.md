---
title: "Customizing Qwen3-8B with Serverless SFT and RLVR on Amazon SageMaker"
slug: "customizing-qwen3-8b-with-serverless-sft-and-rlvr-on-amazon-sagemaker"
description: "Amazon SageMaker now supports a workflow for customizing the Qwen3-8B model using supervised fine-tuning (SFT) and reinforcement learning with verifiable rewards (RLVR) via Group Relative Policy..."
date: 2026-09-15T22:08:30+05:30
tags: [AmazonSageMaker, Qwen3, FineTuning, RLVR, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Computing", "Large Language Models"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-20331-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Customizing Qwen3-8B with Serverless SFT and RLVR on Amazon SageMaker

Amazon SageMaker now supports a workflow for customizing the Qwen3-8B model using supervised fine-tuning (SFT) and reinforcement learning with verifiable rewards (RLVR) via Group Relative Policy Optimization (GRPO).

## 🧩 How it works

The workflow is divided into three primary concerns:

*   **Data Preparation**: The process begins with the Amazon Sales Dataset from Kaggle, containing over 1,000 product records with fields such as product_id, product_name, category, about_product, pricing, ratings, reviews, and product links. This is run as an Amazon SageMaker Processing job to normalize text, remove unusable rows, map information into a nine-category tagging target, and split data into training and validation JSONL files. These are stored in Amazon S3 and registered as versioned datasets in the Amazon SageMaker AI Registry.
*   **Serverless Model Customization**: SFT is used to teach the model the tagging schema, followed by RLVR to optimize behavior against a deterministic reward. This phase uses the Amazon SageMaker Python SDK v3 serverless customization trainers (`SFTTrainer` and `RLVRTrainer`). In this context, "serverless" refers to the training path, where Amazon SageMaker selects and releases training capacity when no compute configuration is supplied.
*   **Inference**: The optimized model is deployed to Amazon SageMaker Asynchronous Inference for batch-oriented catalog enrichment, utilizing a provisioned `ml.g6.2xlarge` instance.

## ⚙️ Key details

| Component | Requirement / Detail |
| :--- | :--- |
| Local Tools | Python 3.11+, AWS CLI v2, pandas, Amazon SageMaker Python SDK v3, and Docker (if building vLLM image) |
| Hosting Quota | `ml.g6.2xlarge` and specific endpoint count for asynchronous endpoint |
| S3 Access | Read/write source catalog, training data, model artifacts, and asynchronous inference requests/outputs |
| ECR Access | Required only if building and hosting the vLLM inference image |
| Training Images | Serverless SFT and RLVR do not require a custom training image |

## 🔍 Permissions

Amazon SageMaker AI permissions are required to manage:
*   Serverless customization jobs
*   AI Registry datasets and evaluators
*   Model package groups, models, and endpoints
*   Asynchronous inference
*   `iam:PassRole` where required

#AmazonSageMaker #Qwen3 #FineTuning #RLVR #MachineLearning

---

*Source: [Build an AI-powered product tagging system with Amazon SageMaker serverless model customization | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-an-ai-powered-product-tagging-system-with-amazon-sagemaker-serverless-model-customization/)*
