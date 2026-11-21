---
title: "Standard Bank Group Automates Generative AI Risk Assessment with AWS"
slug: "standard-bank-group-automates-generative-ai-risk-assessment-with-aws"
description: "Standard Bank Group has deployed an automated assessment system for generative AI use cases, built with AWS Professional Services, that scores each case against international AI standards and..."
date: 2026-11-21T06:15:51+05:30
tags: [GenerativeAI, RiskAssessment, AWS, Bedrock, LLMasJudge, Compliance]
categories: ["AI", "Machine Learning", "AI Governance", "Cloud Computing", "Financial Services"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22493-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Standard Bank Group Automates Generative AI Risk Assessment with AWS

Standard Bank Group has deployed an automated assessment system for generative AI use cases, built with AWS Professional Services, that scores each case against international AI standards and internal policies while operating entirely within the bank's own AWS account.

## 🔍 Overview
- The assessment produces reports and a dashboard showing what controls are already in place, what is working well, and what still needs mitigation.
- The bank already had an established model risk practice covering explainability and fairness, plus a change risk process that assesses each new use case by risk level before it goes live.
- Generative AI increases complexity because models and tooling change every three to six months, yet each use case must still meet the same high security and compliance bar.

## 🧩 How it works
The pipeline runs in four stages:
1. A pre-assessment agent collects evidence about the use case.
2. The pipeline examines the evidence and tests the application directly.
3. The pipeline evaluates that evidence against defined controls.
4. The pipeline summarizes results in a standard, predefined format and delivers them to the people who act on them.

Four kinds of evidence feed the assessment:
- **System documentation** — describes how the application was designed, built, and evaluated.
- **Policy documents** — set out roles, responsibilities, and procedures such as incident handling.
- **Source code and the system prompt** — show how controls are implemented.
- **Live calls to the application** — show how it behaves in practice.

For live testing, the pipeline calls the application through its AWS Lambda function or API. The delivery team supplies questions a typical user would ask. The pipeline adds a built-in set of jailbreak attempts and off-topic questions, which the application is expected to decline. It also sends the same prompt several times, in its original and reworded forms, and uses an embedding model on Amazon Bedrock to check that the answers stay consistent in meaning. Every response is stored in Amazon S3, so reviewers can see exactly what the application generated.

## ⚙️ Key details
- **AWS Well-Architected Tool** handles intake, using a custom lens that holds about 40 questions, each covering a risk event such as incomplete technical documentation or insufficient human oversight.
- **AWS Step Functions** orchestrates the pipeline.
- A **foundation model on Amazon Bedrock** evaluates the evidence using a technique called LLM-as-a-judge, in which a large language model checks evidence against defined criteria.
- A **pre-assessment agent running on AWS Fargate** scans the use case's code repository and documentation, maps relevant files to each question, and pre-populates the lens with answers and links to the evidence.
- **Amazon S3** stores documents, code, and test results in the bank's own bucket.
- Access to the model is controlled through **AWS Identity and Access Management (IAM)**, just as for other AWS workloads.
- Amazon Bedrock does not share the bank's prompts or model outputs with model providers, and does not use them to train models.
- Because Bedrock offers many foundation models through one API, the team can move to a newer judge model by changing a configuration setting instead of rebuilding the pipeline.

## 💡 Why it matters
- The assessment runs entirely in Standard Bank Group's own AWS account, keeping data and evaluation within existing security boundaries.
- The bank continues to use the controls it already runs on AWS, without stepping outside them.
- Model updates are handled through configuration changes, reducing operational overhead as foundation models evolve.
- Full evidence traceability — every response stored in S3 — supports audit and review requirements.

#GenerativeAI #RiskAssessment #AWS #Bedrock #LLMasJudge #Compliance

---

*Source: [How Standard Bank Group automates AI risk assessment for generative AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-standard-bank-group-automates-ai-risk-assessment-for-generative-ai/)*
