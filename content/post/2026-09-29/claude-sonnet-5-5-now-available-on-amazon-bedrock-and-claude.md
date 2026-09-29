---
title: "Claude Sonnet 5.5 Now Available on Amazon Bedrock and Claude Platform on AWS"
slug: "claude-sonnet-5-5-now-available-on-amazon-bedrock-and-claude-platform-on-aws"
description: "Claude Sonnet 5.5 is now available on Amazon Bedrock and the Claude Platform on AWS, providing a smarter and more efficient model for knowledge work and coding."
date: 2026-09-29T12:01:29+05:30
tags: [AWS, AmazonBedrock, Claude, AI, CloudComputing]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/28/ML-22023-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Claude Sonnet 5.5 Now Available on Amazon Bedrock and Claude Platform on AWS

Claude Sonnet 5.5 is now available on Amazon Bedrock and the Claude Platform on AWS, providing a smarter and more efficient model for knowledge work and coding.

## 🔍 Overview
Claude Sonnet 5.5 is designed for tasks where the approach is already clear and requires fast execution. Compared to Claude Opus 5.5, it offers a lower cost per task for most work and operates at a faster speed.

## 💡 Why it matters

| Model | Primary Function and Use Cases |
| :--- | :--- |
| **Claude Sonnet 5.5** | Focused coding and knowledge work; executing clear approaches quickly with lower cost and faster speed. |
| **Claude Opus 5.5** | Judgment calls, release debugging, multi-PR feature stacks, security reviews of large pull requests, code migrations, long analyses, financial research, and contract redlining. |

## ⚙️ Key details

**Coding and Engineering Capabilities:**
* Completes feature assignments or bug fixes and checks results against stated requirements.
* First response to alerts.
* Always-on monitoring of agents.
* SQL generation.
* UI and UX testing.
* Fast coding agents in the IDE with a fixed spend cap.

**Enterprise and Document Capabilities:**
* Produces polished one-pagers, architecture diagrams, and summary slides (improving upon Sonnet 5).
* Scoped analysis.
* Short spreadsheet edits.
* Routine document tasks for large user populations.

**AWS Integration and Security:**
* Data remains within AWS infrastructure with Regional data residency.
* Integrates with AWS Identity and Access Management (IAM) for access.
* Uses AWS CloudTrail for audit and Amazon CloudWatch for monitoring.
* Compatible with Amazon Bedrock Guardrails.
* Usage is billed through the AWS bill.

## 🚀 Availability

**Access Methods:**
* **Console:** Open Amazon Bedrock console > Test > Playground > select Sonnet 5.5.
* **Programmatic:** Call the model via the Anthropic Messages API against bedrock-runtime using the Anthropic SDK.
* **CLI/SDK:** Use Invoke and Converse APIs on bedrock-runtime via the AWS Command Line Interface (AWS CLI) and AWS SDK.

**Deployment:**
* Available on Amazon Bedrock through the Global CRIS (global.) inference profile on bedrock-runtime.
* Available through Claude Platform on AWS in North America.

**Technical Requirements:**
* Active AWS account with Amazon Bedrock access.
* AWS CLI installed and configured.
* Python 3.10+.
* Boto3 installed (`pip install boto3`).
* IAM permissions: `bedrock:InvokeModel` and `bedrock:InvokeModelWithResponseStream`.

Users can monitor performance, usage, and costs through AWS Cost Explorer and Amazon CloudWatch.

#AWS #AmazonBedrock #Claude #AI #CloudComputing

---

*Source: [Introducing Claude Sonnet 5.5 on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-claude-sonnet-5-5-on-aws/)*
