---
title: "Amazon Bedrock Expands Anthropic Claude Model Availability in India, Seoul, and Singapore"
slug: "amazon-bedrock-expands-anthropic-claude-model-availability-in-india-seoul-and-singapore"
description: "Amazon Bedrock has updated its availability for Anthropic Claude models, introducing geographic cross-Region inference in India and in-region inference in Seoul and Singapore."
date: 2026-09-30T12:02:09+05:30
tags: [AmazonBedrock, Anthropic, Claude, AWS, CloudComputing]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Generative AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21953-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Expands Anthropic Claude Model Availability in India, Seoul, and Singapore

Amazon Bedrock has updated its availability for Anthropic Claude models, introducing geographic cross-Region inference in India and in-region inference in Seoul and Singapore.

## 🚀 Availability

| Region | Available Models | Inference Type |
| :--- | :--- | :--- |
| India | Claude Opus 5, Claude Sonnet 5, Claude Haiku 4.5 | Geographic cross-Region |
| Seoul | Claude Opus 5, Claude Sonnet 5 | In-region |
| Singapore | Claude Sonnet 5 | In-region |

## 🧩 How it works

**India Geographic Cross-Region Inference**
* Requests route exclusively between the Mumbai (ap-south-1) and Hyderabad (ap-south-2) Regions.
* Input prompts and output results may move between these two Regions, drawing on a broader pool of compute to maintain throughput and performance during traffic peaks.
* The request originates from the source Region and is automatically routed to a destination Region defined in the inference profile.

**In-Region Inference (Seoul and Singapore)**
* Processing is handled entirely within the single AWS Region specified (ap-northeast-2 for Seoul or ap-southeast-1 for Singapore).
* Input prompts and output results stay within that Region for the full lifecycle of the request.
* Throughput is bounded by the specific Region's capacity and subject to per-Region service quotas.

## ⚙️ Key details

* **Security and Data:** Cross-Region inference uses the secure AWS network with end-to-end encryption for data in transit. Amazon Bedrock employs a zero data retention (ZDR) model by default, meaning model inputs and outputs are not stored. However, human review by AWS may be required if content is flagged by automatic safety classifiers.
* **Integration:** Models can be accessed via the Amazon Bedrock console text playground or programmatically using the Anthropic Messages API, Amazon Bedrock InvokeModel API, and Converse API.
* **Management:** For India cross-Region inference, billing, quota consumption, Amazon CloudWatch metrics, and AWS CloudTrail log entries are tracked in the source Region only.
* **Technical Requirements:** Programmatic access requires Python 3.8+ and the installation of `boto3`, `anthropic`, and `aws_bedrock_token_generator`.

## 💡 Why it matters

These updates allow customers to meet specific requirements for processing data locally in a desired geography. Specifically, the India profile keeps inference within the country, while in-region inference in Seoul and Singapore supports applications with strict data residency requirements.

#AmazonBedrock #Anthropic #Claude #AWS #CloudComputing

---

*Source: [Amazon Bedrock expands Claude model availability to in-country inferencing in India | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-expands-claude-model-availability-to-india-cross-region-inference/)*
*Source: [Introducing Anthropic models on Amazon Bedrock for in-region inference in Seoul and Singapore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-anthropic-models-on-amazon-bedrock-for-in-region-inference-in-seoul-and-singapore/)*
