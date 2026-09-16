---
title: "PII Redaction using Amazon Bedrock Data Automation and Serverless Architecture"
slug: "pii-redaction-using-amazon-bedrock-data-automation-and-serverless-architecture"
description: "Amazon Bedrock Data Automation (BDA) is a service offering from Amazon Bedrock designed to intelligently extract structured information from unstructured documents, images, audio, and video. A new..."
date: 2026-09-16T22:05:42+05:30
tags: [AmazonBedrock, PII, AWS, Serverless, DataAutomation]
categories: ["AI", "Machine Learning", "Cloud Computing", "Data Privacy"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-20554-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# PII Redaction using Amazon Bedrock Data Automation and Serverless Architecture

Amazon Bedrock Data Automation (BDA) is a service offering from Amazon Bedrock designed to intelligently extract structured information from unstructured documents, images, audio, and video. A new implementation demonstrates using BDA with AWS Step Functions and AWS Lambda to create a serverless batch architecture for PII redaction.

## 🧩 How it works

The solution consists of two primary components:
* **Custom BDA Blueprint**: Defines the specific information to be redacted.
* **Serverless Pipeline**: Applies the blueprint at batch scale.

To perform redactions, the system identifies bounding box coordinates for eligible fields, converts PDFs to PNGs, and applies black box redactions at those coordinate locations during post-processing. BDA provides the field content, a confidence score, and the bounding box coordinates for each instance.

## ⚙️ Key details

Users can create BDA blueprints through the AWS Management Console, AWS Command Line Interface (AWS CLI), or developer SDKs. The console includes a walkthrough option to generate a blueprint schema based on a sample document.

### Blueprint Configuration

| Component | Description |
| :--- | :--- |
| **Field Group** | A structure used to organize related results into a single location within an extraction. |
| **Inference Type (Explicit)** | Provides extraction without expected transformations. |
| **Inferred Inference Type** | Allows for transformations, such as date formats. |
| **Natural-Language Instructions** | Used to declare named document fields for precise extraction and scope detection. |

### Use Case: Attending Physician Statements

In a demonstrated use case for PII redactions on Attending Physician Statements, the blueprint schema defines 37 fields across 9 field groups. The system distinguishes between sensitive and non-sensitive information:

* **Sensitive Information (Redacted)**: Patient name, date of birth, home address, and contact information. 
* **Non-Sensitive Information (Retained)**: Physician name, examination dates, office address, office contact information, symptoms, and medical notes.

By using natural-language instructions, BDA can distinguish a patient's date of birth from appointment and signature dates, regardless of the formats appearing on the page. The target information may span structured form fields and unstructured handwriting across multiple instances in a document.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/PII-blog-figure3.png)

#AmazonBedrock #PII #AWS #Serverless #DataAutomation

---

*Source: [Build a serverless PII redaction pipeline with Amazon Bedrock Data Automation | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-serverless-pii-redaction-pipeline-with-amazon-bedrock-data-automation/)*
