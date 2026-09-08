---
title: "DiDi International Business Group deploys AI-based quality assurance on Amazon Bedrock"
description: "DiDi’s International Business Group has partnered with AWS to transition its Customer Experience (CX) department’s quality assurance (QA) system from a third-party solution to a self-owned AI..."
date: 2026-09-08T22:06:20+05:30
tags: [DiDi, AWS, AmazonBedrock, ArtificialIntelligence, CustomerExperience]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21371-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# DiDi International Business Group deploys AI-based quality assurance on Amazon Bedrock

DiDi’s International Business Group has partnered with AWS to transition its Customer Experience (CX) department’s quality assurance (QA) system from a third-party solution to a self-owned AI architecture built on Amazon Bedrock. This system manages quality monitoring for ride-hailing, food delivery, and financial services across 14 countries in Spanish and Portuguese.

## 🧩 How it works

The system utilizes a preprocessing layer to normalize live chat and phone transcripts into a unified format before passing data through three specialized pipelines:

| Pipeline | Function |
| :--- | :--- |
| Intent | Verifies representative contact reason assignment and identifies taxonomy gaps |
| Evaluation | Audits compliance and extracts business insights in a single LLM call |
| Voice of Customer (VOC) | Aggregates ticket batches to surface systemic trends |

## ⚙️ Key details

The implementation of Amazon Bedrock provides several technical advantages for the CX department:

* **Model Flexibility**: Access to a broad selection of foundation models via a single API allows for model-agnostic optimization of each pipeline.
* **Security and Governance**: Utilizes AWS PrivateLink, encryption in transit and at rest, and AWS Identity and Access Management (IAM) to maintain data within DiDi’s network boundary.
* **Responsible AI**: Amazon Bedrock Guardrails provides content filtering and sensitive information redaction.
* **Performance Gains**: Intent verification accuracy improved from 38% to 86%, compliance scoring accuracy exceeded 90%, and VOC analysis reduced summarization time from hours to minutes.

## 💡 Why it matters

By moving to a self-owned architecture, the CX team gains greater transparency and oversight. Each judgment produced by the system includes a complete reasoning chain, ensuring that quality assurance processes align with the company's operational requirements for its millions of users.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21371-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21371-2.png)

#DiDi #AWS #AmazonBedrock #ArtificialIntelligence #CustomerExperience

---

*Source: [How DiDi built intelligent contact center QA with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-didi-built-intelligent-contact-center-qa-with-amazon-bedrock/)*
