---
title: "Social Department Introduces QuickSearch for Entertainment Marketing"
slug: "social-department-introduces-quicksearch-for-entertainment-marketing"
description: "Social Department, the AI operating system for entertainment marketing, set out to encode editorial questions as executable retrieval pipelines, resulting in QuickSearch, a set of single-action..."
date: 2026-11-19T18:06:46+05:30
tags: [ArtificialIntelligence, AmazonBedrock, Entertainment, MachineLearning, AWS]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21816-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Social Department Introduces QuickSearch for Entertainment Marketing

Social Department, the AI operating system for entertainment marketing, set out to encode editorial questions as executable retrieval pipelines, resulting in QuickSearch, a set of single-action queries that return clips marketers are looking for without requiring them to describe it.

## 🔍 Overview

Entertainment marketing teams manage tens of thousands of video assets across studios, networks, and streaming applications. Social Department serves major studios, networks, streamers, and FAST applications by automating campaign strategy, asset creation, publishing, and performance optimization across a client's full content library. Because most of those functions depend on locating the right moment inside footage first, semantic clip discovery has been core to the product from the beginning.

## 🧩 How it works

Content understanding and trend acquisition run as independent pipelines on their own schedules and are joined only when a user selects a QuickSearch action. QuickSearch provides four actions, each with its own retrieval strategy, editorial criteria, and ranking model:

| QuickSearch Action | Description |
| :--- | :--- |
| Shareable Scenes | Surfaces substantial, self-contained scenes such as extended confrontations, climaxes, and set pieces, biased toward developed sequences rather than quick reactions. |
| Quotable Quotes | Finds punchy, quotable dialogue capped at short clip lengths, weighting up lines that have demonstrably circulated where that signal is available for the title. |
| Memeable Moments | Identifies individual frames that will function as memes and generates a caption grounded in the actual frame. |
| Trend Align | Aligns content with current trends. |

## ⚙️ Key details

- The models run on Amazon Bedrock, ensuring customer data stays within the AWS data boundary, is not shared with model providers, and is not used to train the underlying models.
- TwelveLabs’ Marengo 3.0 and Pegasus 1.2 models on Amazon Bedrock provide the scene-level video reasoning the pipeline builds on.
- AWS supplies the infrastructure, model access including Anthropic’s Claude models, and Amazon OpenSearch Serverless for retrieval.
- TrackIt, an AWS Premier Tier Services Partner, implemented and delivered against the design owned by Social Department, which includes the pipeline architecture, retrieval system, and editorial criteria behind each action.

## 💡 Why it matters

Social Department’s approach to responsible AI is that AI proposes and people decide:
- In production, code checks generated output against the source material (for example, a quote is discarded if it isn’t in the episode transcript).
- Amazon Bedrock Guardrails helps screen customer search text for prompt attacks.
- A person on the customer’s team approves every post before it publishes.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21816-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21816-4.jpg)

#ArtificialIntelligence #AmazonBedrock #Entertainment #MachineLearning #AWS

---

*Source: [How Social Department built culture-aware video discovery | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-social-department-built-culture-aware-video-discovery/)*
