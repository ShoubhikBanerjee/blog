---
title: "PolyAI Dialog-RSN-1 available on AWS Marketplace and SageMaker JumpStart"
slug: "polyai-dialog-rsn-1-available-on-aws-marketplace-and-sagemaker-jumpstart"
description: "PolyAI has made Dialog-RSN-1, a reasoning model built for real-time complex dialog, available on AWS Marketplace and Amazon SageMaker JumpStart. This update allows developers to deploy the model as a..."
date: 2026-11-20T22:08:48+05:30
tags: [PolyAI, AWS, AmazonSageMaker, DialogRSN1, RealTimeAI]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Natural Language Processing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22412-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# PolyAI Dialog-RSN-1 available on AWS Marketplace and SageMaker JumpStart

PolyAI has made Dialog-RSN-1, a reasoning model built for real-time complex dialog, available on AWS Marketplace and Amazon SageMaker JumpStart. This update allows developers to deploy the model as a SageMaker endpoint within their own AWS environments, supporting frontier dialog agents that hear live calls, reason about them, and act in real time.

## 🧩 How it works
Dialog-RSN-1 is designed to handle customer conversations by perceiving a caller's audio directly, reasoning about their needs, and responding in real time—all in a single pass. 
- It avoids the traditional tradeoff between speed and understanding by reasoning directly over the caller's audio.
- The model picks up tone, hesitation, and timing signals that plain transcripts often lose, allowing it to decide the right moment to respond.
- It catches hesitation and hears frustration before it escalates, similar to how human agents handle calls.
- Barge-in functionality remains active even during call volume spikes, and responses keep pace with the conversation without lagging.

## ⚙️ Key details
The endpoint speaks the OpenAI Realtime protocol, enabling existing Realtime clients to connect through PolyAI’s bridge by changing their base URL. 

| Feature | Specification |
| :--- | :--- |
| Input Audio | 16-bit PCM mono at 16 or 24 kHz (G.711 or Opus must be transcoded first) |
| Connection Limit | Up to 30 minutes per connection |
| Language Support | English only |
| Protocol | OpenAI Realtime |

## 🚀 Availability and Deployment
Dialog-RSN-1 is the first PolyAI model available through AWS Marketplace. It can be deployed in two primary ways:
- **AWS Marketplace Subscription:** Subscribe via AWS Marketplace and deploy as a SageMaker endpoint inside your own AWS environment.
- **SageMaker JumpStart:** Deploy directly from Amazon SageMaker Studio using the steps in "Deploy and evaluate models with Amazon SageMaker JumpStart." With one-click deployment, SageMaker JumpStart spins up a real-time inference endpoint on a pre-tuned serving stack, eliminating the need for manual container selection or instance type guesswork.

For automated workflows, the same one-click deployment can be executed using a few lines of the SageMaker Python SDK. The Dialog-RSN-1 endpoint runs entirely within the customer's AWS account, deployed in their Virtual Private Cloud (VPC), accessed through IAM roles, and monitored via Amazon CloudWatch logging and metrics. This setup ensures that caller audio and transcripts remain within a controlled boundary, supporting data residency and auditability requirements.

## 💡 Why it matters
By deploying Dialog-RSN-1, customers retain ownership of orchestration, telephony integration, and business logic, while the model handles the complex task of understanding live calls and responding in real time. This approach allows organizations to build dialog agents that hear and handle calls with the nuance of human agents, without the latency penalties associated with separate speech-to-text and reasoning steps.

The model is currently handling live calls in production. Developers can discover and evaluate the model in the SageMaker JumpStart catalog, where overview pages and sample notebooks are provided. A sample notebook allows users to stream recorded caller audio to the deployed endpoint to view the model’s turn decisions, replies, and transcripts before committing to infrastructure.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22412-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22412-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22412-3.png)

#PolyAI #AWS #AmazonSageMaker #DialogRSN1 #RealTimeAI

---

*Source: [PolyAI Dialog-RSN-1 is now on Amazon SageMaker JumpStart | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/polyai-dialog-rsn-1-is-now-on-amazon-sagemaker-jumpstart/)*
