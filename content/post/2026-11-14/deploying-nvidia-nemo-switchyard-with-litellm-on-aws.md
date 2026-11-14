---
title: "Deploying NVIDIA NeMo Switchyard with LiteLLM on AWS"
slug: "deploying-nvidia-nemo-switchyard-with-litellm-on-aws"
description: "LiteLLM now includes a native built-in Switchyard stage router, allowing developers to route AI model requests through an open source gateway. By using the AWS Cloud Development Kit (AWS CDK), you..."
date: 2026-11-14T18:03:06+05:30
tags: [AWS, LiteLLM, NVIDIA, AI, LLM]
categories: ["AI", "Machine Learning", "Cloud Computing", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/11/ML-22318-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Deploying NVIDIA NeMo Switchyard with LiteLLM on AWS

LiteLLM now includes a native built-in Switchyard stage router, allowing developers to route AI model requests through an open source gateway. By using the AWS Cloud Development Kit (AWS CDK), you can deploy this configuration on Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.

## 🧩 How it works

Switchyard acts as a routing plugin that allows an AI agent to choose which model handles each request. The integration functions by sending an OpenAI-compatible request with the model field set to the specific LiteLLM model group. The system operates on Amazon Bedrock using the Converse or ConverseStream API.

## ⚙️ Key details

* Routing Strategies: The plugin supports Stage routing (choosing between two candidates) and Random routing (traffic splits via weight for A/B comparisons).
* Infrastructure: The setup uses an Application Load Balancer, AWS WAF for request filtering, and Amazon Route 53 for hostname resolution.
* Security: AWS Secrets Manager handles gateway keys, and the task security group limits access strictly to the load balancer.
* Monitoring: Logs are maintained in Amazon CloudWatch for 30 days, with metrics collected via Container Insights.

## 🛠 Routing Strategies

| Strategy | Requirements | Function |
| :--- | :--- | :--- |
| Stage | Exactly two candidates | Picks between a capable model and a lower-cost efficient model |
| Random | At least two candidates | Picks from configured models using optional weights |

Note: Classifier-backed strategies, such as Task and Composite routing, require intermediate model calls that this integration does not support.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/11/ML-22318-1.png)

#AWS #LiteLLM #NVIDIA #AI #LLM

---

*Source: [Route coding agent requests to the right model on Amazon Bedrock with NVIDIA NeMo Switchyard | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/route-coding-agent-requests-to-the-right-model-on-amazon-bedrock-with-nvidia-nemo-switchyard/)*
