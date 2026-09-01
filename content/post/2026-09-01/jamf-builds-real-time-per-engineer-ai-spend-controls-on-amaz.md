---
title: "Jamf Builds Real-Time Per-Engineer AI Spend Controls on Amazon Bedrock"
description: "Jamf, an Apple device management company serving more than 76,000 organizations, has deployed a production system that tracks individual engineers' daily Amazon Bedrock spending and enforces tiered..."
date: 2026-09-01T22:04:40+05:30
tags: [AIFinOps, AmazonBedrock, costcontrol, generativeAI, IAMIdentityCenter, tokenomics]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21656-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Jamf Builds Real-Time Per-Engineer AI Spend Controls on Amazon Bedrock

Jamf, an Apple device management company serving more than 76,000 organizations, has deployed a production system that tracks individual engineers' daily Amazon Bedrock spending and enforces tiered model restrictions based on budget thresholds. The solution addresses what the company calls the "tokenomics problem": generative AI spend scales with behavior rather than provisioned capacity, making costs invisible until the bill arrives and complicating both cost control and ROI proof.

## 🔍 The Challenge

Generative AI spend behaves unlike traditional compute costs in several ways:
- Traditional compute scales with provisioned capacity
- AI spend scales with behavior: a single engineer running an agentic coding loop against a premium model can burn more tokens in a few hours than a team does in a week
- Usage is invisible until the bill arrives
- Leadership wants three answers before expanding AI access: What do we spend per person? Can we cap it without slowing engineers down? And do the productivity gains justify the cost?

Jamf gave its engineering organization broad access to Amazon Bedrock to accelerate AI-assisted development. Productivity climbed, but so did the need for AI FinOps: per-user visibility and cost accountability.

## ⚙️ How the Enforcement Works

Jamf's solution tracks each engineer's daily Amazon Bedrock spending and applies tiered model restrictions as they approach their budget:

| Threshold | Action |
|-----------|--------|
| 80% of daily budget | Denies Anthropic Claude Opus access |
| 100% of daily budget | Denies Anthropic Claude Sonnet access |
| Always allowed | Anthropic Claude Haiku (low-cost model remains available) |

Key operational characteristics:
- Restrictions take effect within minutes
- No re-authentication required
- Restrictions revert automatically at the next daily reset
- Documented exception process grants time-boxed higher limits for engineers who legitimately need more

## 🧩 Technical Architecture

The system uses multiple AWS services in a serverless pipeline:

**Data collection and calculation:**
- When an engineer calls Amazon Bedrock (`bedrock:InvokeModel`) through their AWS IAM Identity Center SSO session, Amazon Bedrock logs invocations (including model ID, input and output token counts, and user identity) to an Amazon S3 bucket
- An Amazon Athena view (`bedrock_cost_today`) reads those logs and computes per-user daily spend by multiplying token counts against published model rates
- Athena queries raw logs in place, avoiding a separate data pipeline

**Enforcement cycle:**
- An AWS Lambda enforcement handler runs every 15 minutes, triggered by Amazon EventBridge
- It reads current day spend from the Athena view
- Cross-references an Amazon DynamoDB exceptions table holding custom, time-boxed limits
- Reads each user's previous state from an Amazon DynamoDB state table
- When spend crosses a new threshold, sends a one-time Slack direct message for that tier

**Policy application:**
- For each engineer over threshold, Lambda publishes a new Customer Managed Policy version using `iam:CreatePolicyVersion`
- Policy targets specific users through a `saml:sub` condition key
- CMPs attach to the IAM permission set
- On next Amazon Bedrock call, IAM evaluates the updated policy and allows or denies accordingly

**Pricing configuration:**
- Amazon Bedrock invocation logs land on S3 as JSON
- Athena table created over log location, with view translating token counts to dollars
- View multiplies input and output tokens by published per-token rate for each model, grouped by user identity and current date
- Each model family needs explicit pricing branch
- Unmapped models priced at highest tier as fail-safe (not $0)

## 🚀 Deployment Requirements

To deploy this solution, you need:
- AWS account with permissions to create IAM roles, Customer Managed Policies, AWS Lambda functions, Amazon Athena workgroups, Amazon S3 buckets, and Amazon DynamoDB tables
- AWS IAM Identity Center with a configured permission set assigned to users
- Amazon Bedrock model invocation logging configured to deliver logs to S3
- AWS CLI configured with appropriate credentials
- Slack workspace with app configured for slash commands, interactivity, and bot messages

## 💡 Implementation Resources

The code for this solution is available at: https://github.com/aws-samples/sample-bedrock-spend-enforcement

When implementing, replace rate constants with current Amazon Bedrock pricing for your Region.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21656-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21656-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21656-3.jpeg)

#AIFinOps #AmazonBedrock #costcontrol #generativeAI #IAMIdentityCenter #tokenomics

---

*Source: [Tokenomics at scale: How Jamf built real-time spend enforcement for Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/tokenomics-at-scale-how-jamf-built-real-time-spend-enforcement-for-amazon-bedrock/)*
