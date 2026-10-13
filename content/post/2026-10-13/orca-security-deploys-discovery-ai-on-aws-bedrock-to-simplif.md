---
title: "Orca Security Deploys Discovery AI on AWS Bedrock to Simplify Cloud Queries"
slug: "orca-security-deploys-discovery-ai-on-aws-bedrock-to-simplify-cloud-queries"
description: "Orca Security has released an update to its Discovery AI service, a natural‑language query agent built on Amazon Bedrock that translates plain‑English questions into Sonar queries for its..."
date: 2026-10-13T22:07:53+05:30
tags: [OrcaSecurity, AmazonBedrock, DiscoveryAI, CloudSecurity]
categories: ["AI", "Cloud Security", "AI Agents", "Machine Learning", "Infrastructure Security"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21130-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Orca Security Deploys Discovery AI on AWS Bedrock to Simplify Cloud Queries

Orca Security has released an update to its Discovery AI service, a natural‑language query agent built on Amazon Bedrock that translates plain‑English questions into Sonar queries for its cloud‑security data graph.

## 🔍 Overview
- Security analysts need fast answers about their cloud infrastructure without deep familiarity with domain‑specific query languages.
- Orca Security’s Sonar system tracks more than 900 cloud resource models (e.g., Amazon EC2 instances, Amazon S3 buckets) and requires JSON queries that specify exact model names, select from 18 operators, and navigate parent‑child hierarchies.
- The original proof‑of‑concept loaded the full Sonar schema (over 900 model definitions) into a single prompt, yielding strong output but high token consumption (~2 million input tokens per workload), high latency (~60 seconds), and limited accuracy on complex multi‑model queries.
- To address these issues, Orca partnered with AWS to build Discovery AI, a hybrid Retrieval‑Augmented Generation (RAG) solution on Amazon Bedrock that converts natural language into validated Discovery filters.

## 🧩 How It Works
Discovery AI follows a nine‑step pipeline, matching each stage to the most suitable Bedrock model:
1. **Request Entry and Context Setup** – Combines the user’s question with organization, connected cloud providers, and request metadata.
2. **Quick Deterministic Matcher** – Uses regex and rule‑based matching to detect high‑confidence patterns such as IP addresses, CVEs, ARNs, file hashes, AMI IDs, Oracle Cloud identifiers, EC2 IDs, URLs, and alert IDs.
3. **Fast‑Path Return** – When a deterministic match is found, a predefined Discovery filter is returned without invoking an LLM.
4. **(Subsequent stages)** – For unmatched requests, the pipeline proceeds through retrieval, schema‑aware construction, and LLM inference stages to produce a Sonar‑compatible JSON query.

Key design choices:
- Amazon Bedrock provides access to multiple foundation models through a single API, allowing the team to allocate different models to each pipeline stage without separate integrations.
- Bedrock inherits AWS governance controls (IAM, VPC endpoints, CloudTrail), satisfying Orca’s security requirements.
- The model‑agnostic architecture enables swapping newer model versions without re‑architecting the pipeline.

## ⚙️ Key Results
- Query costs reduced by **90 %** compared with the baseline.
- Input token usage reduced by **93 %**.
- End‑to‑end latency reduced by **75 %**, achieving ~15‑second response times (down from ~60 seconds).
- The system now handles thousands of queries per day.

## 💡 Why It Matters
- Analysts can obtain answers without knowing Sonar’s exact schema or the 18‑operator query language.
- Lower costs and faster responses make continuous cloud‑security monitoring more practical.
- The hybrid RAG approach demonstrates how Retrieval‑Augmented Generation can be combined with domain‑specific schemas to improve accuracy on complex multi‑model queries.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21130-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21130-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21130-3.jpg)

#OrcaSecurity #AmazonBedrock #DiscoveryAI #CloudSecurity

---

*Source: [Natural language security queries at Orca Security using Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/natural-language-security-queries-at-orca-security-using-amazon-bedrock/)*
