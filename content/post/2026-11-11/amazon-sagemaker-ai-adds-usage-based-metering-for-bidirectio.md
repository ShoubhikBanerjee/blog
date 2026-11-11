---
title: "Amazon SageMaker AI Adds Usage-Based Metering for Bidirectional Streaming Inference"
slug: "amazon-sagemaker-ai-adds-usage-based-metering-for-bidirectional-streaming-inference"
description: "Amazon has announced usage-based metering for Amazon SageMaker bidirectional (bidi) streaming inference. This update allows model providers to report actual usage for AWS Marketplace software..."
date: 2026-11-11T22:05:42+05:30
tags: [AmazonSageMaker, AWSMarketplace, Deepgram, RealTimeAI, CloudBilling]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-21045-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI Adds Usage-Based Metering for Bidirectional Streaming Inference

Amazon has announced usage-based metering for Amazon SageMaker bidirectional (bidi) streaming inference. This update allows model providers to report actual usage for AWS Marketplace software charges, addressing a specific billing challenge for real-time speech AI applications.

## 🔍 Overview
This capability builds on the previously introduced bidirectional streaming for real-time inference on Amazon SageMaker AI. Deepgram, a real-time speech AI company, serves as the launch partner, bringing usage-based Speech-to-Text (STT) and Text-to-Speech (TTS) billing to the AWS Marketplace. 

Deepgram has also enhanced its support with AWS Identity and Access Management (AWS IAM) temporary delegation to simplify secure authentication and expanded its observability with enhanced metrics.

## 🧩 How it works
The solution introduces a dual-connection architecture to separate inference data from billing metadata:

| Connection | Purpose |
| :--- | :--- |
| Data connection | Carries inference request and response data through the existing bidirectional stream. |
| Metadata connection | A companion WebSocket dedicated specifically to metering data. |

In this workflow, a client streams audio and receives transcriptions through the SageMaker AI API using an HTTP/2 event stream. SageMaker AI then connects to the model server over WebSockets. Both connections utilize the same `X-Amzn-SageMaker-Request-Id` header, allowing the model server to correlate metering records with active inference sessions.

## ⚙️ Key details
Providers can align AWS Marketplace software charges with reported usage through several technical specifications:

*   **Opt-in Mechanism:** Model servers opt in by returning the header `X-Amzn-SageMaker-Metadata-Stream-Supported: true` during the WebSocket upgrade.
*   **Message Format:** Metering data is sent as JSON text frames. Each frame must contain exactly one metering record rather than an array.
*   **Quotas:** The metadata stream has a rate quota of one message per second per connection, with a maximum message size of 512 bytes.
*   **Billing Dimensions:** Messages use the `inference.count` dimension, while the `ConsumedUnits` field supplies the quantity (e.g., reporting 720 seconds for 12 minutes of audio).
*   **Reliability:** The metadata connection runs over TCP for ordered, reliable delivery. The `ClientToken` field supports idempotency, and duplicate tokens are dropped silently.

## 💡 Why it matters
For organizations deploying models for transcription, contact centers, voice agents, or captioning, this update enables transparent, per-unit billing. Usage-based charges flow directly into the AWS bill, though Amazon SageMaker AI endpoint infrastructure charges still apply independently. Providers can also set `X-Amzn-SageMaker-Metadata-Stream-Required` to true to ensure inference stops if the metadata stream becomes unavailable.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/07/16/ML-21067-6.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2024/09/10/llinx.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/07/21/Screenshot-2026-07-21-at-11.30.35%E2%80%AFAM.png)

#AmazonSageMaker #AWSMarketplace #Deepgram #RealTimeAI #CloudBilling

---

*Source: [Introducing usage-based pricing for Amazon SageMaker AI bidirectional streaming | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-usage-based-pricing-for-amazon-sagemaker-ai-bidirectional-streaming/)*
