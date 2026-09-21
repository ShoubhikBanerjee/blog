---
title: "EXL Launches AI-Powered Medical Document Processing Solution on AWS"
slug: "exl-launches-ai-powered-medical-document-processing-solution-on-aws"
description: "Insurance claims adjusters typically spend over 100 minutes per case manually reviewing medical records, which are often unstructured and contain specialized clinical terminology. EXL has introduced..."
date: 2026-09-21T22:03:11+05:30
tags: [AWS, Insurance, GenerativeAI, HealthTech, DocumentProcessing]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/ML-21250-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# EXL Launches AI-Powered Medical Document Processing Solution on AWS

Insurance claims adjusters typically spend over 100 minutes per case manually reviewing medical records, which are often unstructured and contain specialized clinical terminology. EXL has introduced an AI-powered Medical intelligent document processing (IDP) solution built on AWS to automate the extraction, summarization, and querying of this data at an enterprise scale.

## 🧩 How it works

The solution utilizes two primary components to manage medical information:

* Xtrakto.AI: A template-agnostic IDP application that uses computer vision, natural language processing, and agentic AI workflows to ingest, classify, and extract data.
* EXL Insurance LLM: A domain-specific intelligence layer fine-tuned on insurance and medical data, including ICD and CPT codes, to perform medical summarization, natural-language querying, and structured output generation.

## ⚙️ Key details

The architecture uses an 11-step workflow managed within AWS, incorporating the following services:

| Service | Role in Workflow |
| :--- | :--- |
| Amazon API Gateway | Secure ingestion and results delivery |
| Amazon Cognito | Request authentication and authorization |
| AWS Step Functions | Orchestration engine for sub-requests and routing |
| Amazon Textract & AWS Lambda | Document preprocessing and OCR |
| Amazon SageMaker AI | Managed training, inference, and domain model hosting |
| Amazon Bedrock | On-demand access to general-purpose foundation models |
| Amazon DynamoDB & RDS | Data enrichment using reference databases |
| Amazon S3 | Central data lake for storage |
| Amazon CloudWatch | Application and model monitoring |

## 💡 Why it matters

By combining domain-specific LLMs with agentic workflows, the solution addresses the challenge of connecting disparate data points across various medical document types, such as diagnostic tests, operative reports, lab results, and psychiatric evaluations. The system operates within an AWS Region with security controls maintained by AWS Identity and Access Management (IAM), ensuring the protection of health information throughout the lifecycle of the claim.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/ML-21250-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/ML-21250-3.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/ML-21250-4.jpg)

#AWS #Insurance #GenerativeAI #HealthTech #DocumentProcessing

---

*Source: [Reducing medical claims review time with AI on AWS: The EXL Medical IDP solution | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/reducing-medical-claims-review-time-with-ai-on-aws-the-exl-medical-idp-solution/)*
