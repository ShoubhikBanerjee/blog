---
title: "Condé Nast Deploys AI Multimodal Video Discovery Solution via AWS"
slug: "conde-nast-deploys-ai-multimodal-video-discovery-solution-via-aws"
description: "Condé Nast partnered with the AWS Generative AI Innovation Center (GenAIIC) to build an AI-powered multimodal video discovery solution to address operational drag across brands including Vogue, GQ,..."
date: 2026-09-29T22:02:51+05:30
tags: [AWS, CondéNast, GenerativeAI, MultimodalSearch, AmazonBedrock]
categories: ["AI", "Machine Learning", "Computer Vision", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/18/ML-21598-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Condé Nast Deploys AI Multimodal Video Discovery Solution via AWS

Condé Nast partnered with the AWS Generative AI Innovation Center (GenAIIC) to build an AI-powered multimodal video discovery solution to address operational drag across brands including Vogue, GQ, Vanity Fair, and Wired.

## 💡 Why it matters

Before the implementation, teams spent an average of 250 minutes per content discovery task manually scrubbing through a library of more than 140,000 videos. The new solution reduced this discovery time to under 2 minutes per task.

## 🔍 Overview

The solution utilizes intent-based semantic search rather than string matching, allowing users to find content based on meaning. Capabilities include:

* **Natural Language Queries:** Users can search for terms such as “beginner yoga content” or “celebrity interview about sustainability.”
* **Multimodal Search:** The system simultaneously scans video transcripts, visual elements, and audio.
* **Visual Search:** Users can upload a reference image to locate visually similar content in the archive.
* **Precise Localization:** Results provide exact timestamps, eliminating the need to watch entire clips.

## 🧩 How it works

The architecture is split into two decoupled planes to separate compute-heavy embedding generation from low-latency search serving:

| Component | Function |
| :--- | :--- |
| Amazon S3 | Holds the source video outputs |
| Amazon ECS with AWS Fargate | Validates video, extracts metadata, and splits video into segments |
| TwelveLabs Marengo Model | Jointly encodes visual, audio, and transcript signals into multimodal vector embeddings |
| Amazon OpenSearch Service | Indexes embeddings and provides managed k-nearest neighbor (k-NN) search with multi-AZ replication |
| Query Tier | Converts natural language into vector searches and returns precise timestamps |

## ⚙️ Key details

* **Model Access:** The TwelveLabs Marengo model is accessed via Amazon Bedrock, which provides multiple foundation models through a single API.
* **Governance:** The system employs AWS Identity and Access Management (IAM) for access, Amazon VPC for network isolation, and AWS CloudTrail for auditability.
* **Scalability:** An Auto Scaling group scales the ingestion service horizontally across multiple Availability Zones to process video chunks in parallel.

#AWS #CondéNast #GenerativeAI #MultimodalSearch #AmazonBedrock

---

*Source: [How Condé Nast built multimodal video discovery with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-conde-nast-built-multimodal-video-discovery-with-amazon-bedrock/)*
