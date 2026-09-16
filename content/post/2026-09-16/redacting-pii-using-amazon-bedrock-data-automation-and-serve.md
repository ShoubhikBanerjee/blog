---
title: "Redacting PII Using Amazon Bedrock Data Automation and Serverless Architecture"
slug: "redacting-pii-using-amazon-bedrock-data-automation-and-serverless-architecture"
description: "Amazon Bedrock Data Automation (BDA) is a service that extracts structured information from unstructured documents, images, audio, and video. A new serverless batch architecture utilizes BDA..."
date: 2026-09-17T00:50:10+05:30
tags: [AmazonBedrock, PII, AWS, Serverless, DataAutomation]
categories: ["AI", "Machine Learning", "Cloud Computing", "Data Privacy"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-20554-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Redacting PII Using Amazon Bedrock Data Automation and Serverless Architecture

Amazon Bedrock Data Automation (BDA) is a service that extracts structured information from unstructured documents, images, audio, and video. A new serverless batch architecture utilizes BDA alongside AWS Step Functions and AWS Lambda to perform PII redaction on Attending Physician Statements before claim processing.

## 🧩 How it works

The solution consists of two primary components:

* **Custom BDA Blueprint**: Defines the specific information to be redacted.
* **Serverless Pipeline**: Applies the blueprint at batch scale using outlined best practices.

To remove sensitive information, the system identifies bounding box coordinates for eligible fields, converts PDFs to PNGs, and applies black box redactions at those coordinate locations during post-processing.

## ⚙️ Key details

Users can create BDA blueprints via the AWS Management Console, AWS CLI, or developer SDKs. The console includes a walkthrough to generate a schema based on a sample document. 

### Blueprint Specifications

| Element | Description |
| :--- | :--- |
| **Schema Requirements** | Must enumerate fields for redaction, data type, natural language description, and applicable transformations. |
| **Inference Type** | "Explicit" provides extraction without expected transformations. |
| **Field Group** | A structure used to organize related results into a single location within an extraction. |
| **Instructions** | Plain-language instructions used to declare named document fields for precise extraction. |

In the Attending Physician Statements use case, the full blueprint schema defines 37 fields across 9 field groups. Each field uses `inferenceType: "explicit"` and natural-language instructions to scope detection.

## 🔍 PII Redaction Logic

 The system uses instructions to distinguish between sensitive and non-sensitive data:

* **Sensitive Information (Redacted)**: Patient name, date of birth, home address, and contact information.
* **Non-Sensitive Information (Preserved)**: Physician name, examination dates, office address, office contact information, symptoms, and medical notes.

These instructions allow BDA to isolate the patient's date of birth from appointment or signature dates, even when multiple formats appear on one page, while ensuring the attending physician's signature and printed name remain outside the redaction set.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/PII-blog-figure3.png)

#AmazonBedrock #PII #AWS #Serverless #DataAutomation

---

*Source: [Build a serverless PII redaction pipeline with Amazon Bedrock Data Automation | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-serverless-pii-redaction-pipeline-with-amazon-bedrock-data-automation/)*
