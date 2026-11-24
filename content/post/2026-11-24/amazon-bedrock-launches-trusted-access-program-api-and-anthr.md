---
title: "Amazon Bedrock Launches Trusted Access Program API and Anthropic Enterprise Safeguards"
slug: "amazon-bedrock-launches-trusted-access-program-api-and-anthropic-enterprise-safeguards"
description: "Amazon Web Services has announced the general availability of the trusted access program API on Amazon Bedrock, along with the public preview of two new security-focused offerings developed in..."
date: 2026-11-24T18:09:57+05:30
tags: [AWS, AmazonBedrock, AISecurity, Anthropic, EnterpriseAI, MachineLearning]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Cybersecurity", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/23/ML-22385-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Launches Trusted Access Program API and Anthropic Enterprise Safeguards

Amazon Web Services has announced the general availability of the trusted access program API on Amazon Bedrock, along with the public preview of two new security-focused offerings developed in partnership with Anthropic. The API provides a centralized way for users to discover, request, and enroll in model provider trusted access programs.

## 🔍 Overview
The new trusted access program API on Amazon Bedrock enables developers to manage access to enterprise-grade AI models through a unified interface. The first two offerings now in public preview are Anthropic’s Enterprise Frontier Safeguards (EFS) and Enterprise Data Controls (EDC), which can be used with Claude Fable, Claude Mythos, Claude Opus 5.5, and Claude Sonnet 5.5 via the Cyber Verification Program (CVP).

## 🧩 How it works
Administrators control enrollment using existing IAM policies and service control policies. The system integrates with AWS Key Management Service (AWS KMS) and Amazon Simple Storage Service (Amazon S3), accessing encrypted data through user-defined key and bucket policies. Users can revoke access at any time, but affected models stop serving within 24 hours of access loss.

## ⚙️ Key details
- EFS and EDC were built in partnership between AWS and Anthropic
- EFS: Customer data stored in their own AWS account; prompts and completions not retained by Anthropic or Amazon Bedrock
- EDC: Data stored in Amazon-managed storage; prompts and completions not retained by Anthropic
- Only automated safety monitoring within AWS reads retained inputs and outputs
- AWS human reviewers do not review content for EFS
- Bedrock writes prompts and responses to retention and key services, encrypted with user’s KMS key or to their S3 bucket
- Data is written to S3 within minutes; retry attempts allowed up to 72 hours for certain failures
- Automated safety monitoring scans data for misuse and creates risk cases in user buckets when needed

## 🚀 Availability
The trusted access program API is generally available. Enterprise Frontier Safeguards (EFS) and Enterprise Data Controls (EDC) are available in public preview on Amazon Bedrock.

#AWS #AmazonBedrock #AISecurity #Anthropic #EnterpriseAI #MachineLearning

---

*Source: [Introducing the Amazon Bedrock Trusted Access API with Anthropic’s Enterprise Frontier Safeguards and Enterprise Data Controls | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-the-amazon-bedrock-trusted-access-api-with-anthropics-enterprise-frontier-safeguards-and-enterprise-data-controls/)*
