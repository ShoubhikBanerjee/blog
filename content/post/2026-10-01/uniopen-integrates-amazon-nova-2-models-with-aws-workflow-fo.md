---
title: "Uniopen integrates Amazon Nova 2 models with AWS workflow for business‑specific moderation"
slug: "uniopen-integrates-amazon-nova-2-models-with-aws-workflow-for-businessspecific-moderation"
description: "Uniopen, the digital communication and membership platform from Taiwan’s Uni‑President Enterprises Group, has updated its moderation system by fine‑tuning Amazon Nova 2 Lite and adding a controlled..."
date: 2026-10-01T22:03:23+05:30
tags: [uniopen, AmazonNova, AWS, moderation]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Governance", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/14/ML-21411-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Uniopen integrates Amazon Nova 2 models with AWS workflow for business‑specific moderation

Uniopen, the digital communication and membership platform from Taiwan’s Uni‑President Enterprises Group, has updated its moderation system by fine‑tuning Amazon Nova 2 Lite and adding a controlled workflow using AWS services.

## 🔍 Overview
- uniopen connects customers to e‑commerce, membership benefits, and other retail experiences across web, tablet, and mobile channels.  
- Its moderation policy classifies each interaction along two axes: the behavior (nine categories) and the subject (brand, other, or forbidden).  Both classifications must be correct for a decision to be useful, and the taxonomy is specific to uniopen’s business.

## 🛠️ How it works
- The team adapted **Amazon Nova 2 Lite** to the business‑specific moderation policies through supervised fine‑tuning in **Amazon SageMaker AI** and a final prompt‑level output optimization.  
- The AWS approach kept correction data, managed training, evaluation, and deployment controls in one repeatable workflow.  
- Model availability varies by AWS Region.

## ⚙️ Architecture
| Component | Role |
|---|---|
| Amazon Nova 2 Lite | Handles primary moderation requests |
| Amazon Nova 2 Pro | Generates candidate corrections for reported errors (human‑verified before training) |
| Amazon S3 | Stores verified correction set and training data |
| Amazon DynamoDB | Tracks active and candidate model configurations |
| Argo Workflows on Amazon EKS | Orchestrates prompt optimization, evaluation, and deployment |
| Argo CD | Applies approved configurations to production |
| Amazon SNS & CloudWatch | Notify operators of hard‑gate failures or candidate attention needed |
| Amazon Bedrock Guardrails | Content filters applied to inputs and outputs |

## 📊 Controls & Governance
- Human review is mandatory for ambiguous cases and for corrections reused as training data.
- Fixed test sets and regression checks prevent automatic promotion when quality declines.
- Two kinds of gates control promotion:
  - **Hard gates** – must‑pass regression tests; a failure stops the workflow and triggers an alert.
  - **Soft gates** – warning signals such as low confidence or a drop in performance for a specific class.
- Responsible AI controls complement model customization, including monitoring errors across behavior and subject categories, minimizing retained customer data, and revalidating thresholds as moderation policies change.

## 🚀 Availability
- The moderation models run across uniopen’s web, tablet, and mobile experiences, using the same taxonomy and release criteria to maintain consistent decisions as interaction formats and topics evolve.
- Deployment to production occurs only after a candidate passes all required hard and soft gates.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/14/ML-21411-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/14/ML-21411-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/14/ML-21411-3.png)

#uniopen #AmazonNova #AWS #moderation

---

*Source: [How uniopen customized Amazon Nova to their retail moderation policies for production deployment | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-uniopen-customized-amazon-nova-to-their-retail-moderation-policies-for-production-deployment/)*
