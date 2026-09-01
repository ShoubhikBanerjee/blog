---
title: "ZS Associates Deploys Enterprise ML Operations Platform Using Amazon SageMaker Studio"
description: "This blog post is co-written with Kiran Dhamane, Abhishek I S, and Mayur Ghodekar from ZS Associates. ZS has selected Amazon SageMaker Studio as the foundation for its enterprise ML operations,..."
date: 2026-09-01T22:04:40+05:30
tags: [AmazonSageMaker, MLOps, AWS, EnterpriseAI, HealthcareCompliance]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/21/ML-20828-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# ZS Associates Deploys Enterprise ML Operations Platform Using Amazon SageMaker Studio

This blog post is co-written with Kiran Dhamane, Abhishek I S, and Mayur Ghodekar from ZS Associates. ZS has selected Amazon SageMaker Studio as the foundation for its enterprise ML operations, establishing it as the primary ad-hoc analytics tool for most application team members.

## 🔍 Overview
ZS implemented a comprehensive security framework to allow data scientists and analysts to access ML capabilities while maintaining compliance with healthcare sector requirements. The platform currently operates at scale with the following metrics:
* 200+ SageMaker domains deployed across multiple AWS accounts
* 500+ to 1,000+ daily active users
* Monthly SageMaker spend exceeding $50K

## 🧩 How it works
The platform utilizes a multi-tenant architecture where each tenant has a separate Amazon SageMaker domain. Each domain maintains isolated AWS Identity and Access Management (IAM) roles, controllable network settings, and isolated Amazon Elastic File System (Amazon EFS) volumes.

### Security and Network Architecture
* **Internet-Free Mode**: The solution runs in internet-free mode by default, using Amazon Virtual Private Cloud (Amazon VPC) endpoints for controlled communication with AWS services.
* **Package Management**: ZS integrated JFrog Artifactory with real-time package scanning and upward repository linking to prevent tampered or unauthorized code.
* **Encryption**: AWS Key Management Service (AWS KMS) encryption is enabled by default for Amazon EFS volumes, Amazon Simple Storage Service (Amazon S3) buckets, Amazon Elastic Container Registry (Amazon ECR), and AWS CodeCommit repositories.
* **Threat Detection and Auditing**: The platform integrates CrowdStrike for OS-level threat detection, Splunk for log aggregation, and AWS CloudTrail for API call logging.

### Access Control
ZS uses a three-tier IAM role structure to manage permissions:

| Role Type | Purpose |
| :--- | :--- |
| Domain Execution Roles | Serve as defaults for users |
| Studio User Roles | Override domain defaults for fine-grained control |
| Space Execution Roles | Govern shared workspaces |

Additionally, IAM policies restrict access to Amazon SageMaker JumpStart, Amazon SageMaker Autopilot, and Amazon SageMaker Data Wrangler based on user roles. Notebook Jobs require explicit IAM Role ARNs for execution.

## ⚙️ Key details
To address specific operational needs, ZS developed custom implementations:
* **Backup Strategy**: Because SageMaker lacks native backup, ZS built a custom lifecycle configuration to sync user data and scripts to Amazon S3. They also use AWS Backup with tag-based automation for Amazon EFS volumes tagged "ZS_Backup," which are stored in dedicated backup vaults.
* **Cost Management**: IAM policies restrict users to smaller, pre-approved instance types. Every resource is tagged by project and team, allowing AWS Cost Explorer to provide visibility. Lifecycle policies automatically shut down inactive resources, and SageMaker Savings Plans reduce monthly spend by approximately $10K.
* **Self-Service**: Streamlit-based tooling and automated lifecycle configurations have reduced dependency on the AWS Management Console and manual compliance overhead.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/21/ML-20828-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/21/ML-20828-2.png)

#AmazonSageMaker #MLOps #AWS #EnterpriseAI #HealthcareCompliance

---

*Source: [How ZS democratized secure ad-hoc analytics with Amazon SageMaker | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-zs-democratized-secure-ad-hoc-analytics-with-amazon-sagemaker/)*
