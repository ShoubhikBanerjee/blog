---
title: "New AWS automation simplifies activation of Bedrock private‑pricing entitlements across organizations"
slug: "new-aws-automation-simplifies-activation-of-bedrock-privatepricing-entitlements-across-organizations"
description: "Amazon Bedrock with managed entitlements simplifies multi‑account access to third‑party AI models by allowing a single subscription from a central account and distribution across an organization...."
date: 2026-10-14T22:09:38+05:30
tags: [AWS, AmazonBedrock, LicenseManager, CDK]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Infrastructure Automation"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-21638-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# New AWS automation simplifies activation of Bedrock private‑pricing entitlements across organizations

Amazon Bedrock with managed entitlements simplifies multi‑account access to third‑party AI models by allowing a single subscription from a central account and distribution across an organization. After a private pricing offer is accepted, AWS Marketplace creates a license in AWS License Manager, which must be activated. AWS now offers two ways to activate these entitlements.

## 🔍 Overview
- Managed entitlements let you subscribe once from a central account and distribute access to third‑party models across your organization.
- Private Pricing Offers let you negotiate custom rates for third‑party models on Amazon Bedrock.
- Once an eligible private offer is accepted, AWS Marketplace creates a license in AWS License Manager that starts in a **Disabled** state.

## 🛠️ Activation Options
| Path | When to use | Core behavior |
|------|-------------|---------------|
| Lightweight script | One‑time, no‑infrastructure fix for trusted licenses | Lists received licenses and prints a dry‑run plan |
| CDK automation | Ongoing, event‑driven processing | Verifies sellers, creates distributed grants, retries activation as needed |

## ⚙️ How the CDK Automation Works
- **Amazon EventBridge rule** listens for AWS Marketplace agreement events on the default event bus in **us-east-1**. It matches source `aws.agreement-marketplace` and detail type `Purchase Agreement Created - Acceptor`, then invokes the Lambda function.
- **AWS Lambda function** receives the agreement event, checks the seller against an allow‑list, discovers the associated license, creates the distributed grant, and requests activation with `CreateGrantVersion(Status=ACTIVE)`.
- The CDK stack is deployed in the AWS Organizations management account using Python 3.12+, the AWS CLI, and AWS CDK v2.
- The stack retries activation when License Manager reports that more time is required.

## 📋 Key Details
- Grants can target the whole organization, selected organizational units (OUs), or specific accounts.
- In AWS Organizations with all features enabled, organization‑level grants are auto‑accepted but remain **Disabled** until you activate them.
- Negotiated pricing applies only after the grant reaches **ACTIVE** or **WORKFLOW_COMPLETED**.
- SaaS products are out of scope for this automation.
- Confirm that the private offer is for a License Manager‑backed Bedrock model before running the automation.

## 🚀 Availability
- Requires an AWS Organizations management account in **us-east-1**.
- All Organization features must be enabled.
- Requires Python 3.12+, AWS CLI, and AWS CDK v2 configured.
- Works with third‑party AI models on Amazon Bedrock that are offered through AWS Marketplace Private Pricing Offers.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/08/21638-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-21638-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-21638-2.jpg)

#AWS #AmazonBedrock #LicenseManager #CDK

---

*Source: [Manage private pricing offers for Amazon Bedrock with managed entitlements | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/manage-private-pricing-offers-for-amazon-bedrock-with-managed-entitlements/)*
