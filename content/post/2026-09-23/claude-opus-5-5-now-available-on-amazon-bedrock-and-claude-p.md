---
title: "Claude Opus 5.5 Now Available on Amazon Bedrock and Claude Platform"
slug: "claude-opus-5-5-now-available-on-amazon-bedrock-and-claude-platform"
description: "Anthropic has announced the availability of Claude Opus 5.5, the first model in the Claude 5.5 model family, now accessible via Amazon Bedrock and Claude Platform on AWS."
date: 2026-09-23T12:05:26+05:30
tags: [Anthropic, AWS, AmazonBedrock, ClaudeOpus, LLM]
categories: ["AI", "Machine Learning", "Cloud Computing", "AI Agents"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/22/ML-22003-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Claude Opus 5.5 Now Available on Amazon Bedrock and Claude Platform

Anthropic has announced the availability of Claude Opus 5.5, the first model in the Claude 5.5 model family, now accessible via Amazon Bedrock and Claude Platform on AWS.

## 🔍 Overview
Claude Opus 5.5 is described as Anthropic’s most capable Opus model, specifically designed for:
* Agentic coding
* Knowledge work
* Long-running tasks

## ⚙️ Key details

| Feature | Description |
| :--- | :--- |
| Adaptive Thinking | Always on; the model decides the reasoning amount needed for each task. |
| Effort Control | Users can use effort as a control instead of manual thinking budgets. |
| Safety Classifiers | First Opus model with classifiers for biology, cyber security, and AI development (similar to Claude Fable 5.1). |
| Communication | Trained to communicate more clearly. |

## 💡 Why it matters

**Efficiency and Cost**
According to Anthropic, Claude Opus 5.5 does more with fewer tokens than Claude Opus 5. Efficiency gains are paired with lower per-token prices and cheaper cache reads, resulting in an average lower cost per task than Claude Opus 5.

**Performance Improvements**
* **Software Development:** An improvement over Opus 5 for longer-running sessions, offering better explainability and communication.
* **Knowledge Work:** Requires fewer corrections than Opus 5 when creating and working with long reports and documents.

**Safety Note**
Requests will be refused more frequently compared to previous Opus versions due to the integrated safety classifiers.

## 🚀 Availability

**Access Methods**
* **Console:** Through the Amazon Bedrock console (Test > Playground).
* **Programmatic:** Via the Anthropic Messages API against `bedrock-runtime` and `bedrock-mantle` (using the Anthropic SDK).
* **CLI/SDK:** Using Invoke and Converse APIs on `bedrock-runtime` via the AWS CLI and AWS SDK.
* **Other:** Available through Claude Platform on AWS in North America and via Getting Started notebooks on GitHub.

**Regional Availability**
* **bedrock-runtime:** Available through US Geo CRIS (us.), EU Geo CRIS (eu.), AU Geo CRIS (au.), JP Geo CRIS (jp.), and Global CRIS (global.) inference profiles.
* **bedrock-mantle:** Runs in the US East (N. Virginia) Region (us-east-1) and AP SouthEast (Melbourne) Region (ap-southeast-4).

#Anthropic #AWS #AmazonBedrock #ClaudeOpus #LLM

---

*Source: [Claude Opus 5.5 is now available on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/claude-opus-5-5-is-now-available-on-aws/)*
