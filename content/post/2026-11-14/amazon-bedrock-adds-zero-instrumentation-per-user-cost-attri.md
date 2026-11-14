---
title: "Amazon Bedrock adds zero‑instrumentation per‑user cost attribution via IAM identity"
slug: "amazon-bedrock-adds-zeroinstrumentation-peruser-cost-attribution-via-iam-identity"
description: "Amazon Bedrock now provides built‑in, zero‑instrumentation cost attribution that traces every inference call back to the IAM principal that made it."
date: 2026-11-14T06:11:11+05:30
tags: [AWS, AmazonBedrock, CostManagement, IAM]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Cost Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-21035-featured-image-2.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock adds zero‑instrumentation per‑user cost attribution via IAM identity

Amazon Bedrock now provides built‑in, zero‑instrumentation cost attribution that traces every inference call back to the IAM principal that made it.

## 🔍 Overview
- Bedrock records the IAM identity of every inference caller with no changes required to your API calls.
- The captured IAM ARN (including session name for federated users) is published to AWS Cost and Usage Report (CUR 2.0) in the `line_item_iam_principal` column.
- Identity flows along with organizational tags into CUR 2.0 and AWS Cost Explorer while remaining inside the AWS security boundary.

## 🧩 How it works
- Inference requests go through one of two Bedrock endpoints: `bedrock-runtime` or `bedrock-mantle`.
- Attribution operates at the endpoint layer, beneath any tool‑specific logic.
- When a user invokes a model, Bedrock captures the full IAM ARN and adds it to CUR 2.0.
- In billing data, usage is aggregated per principal and per usage type for each export interval (hourly or daily).
- Per‑request cost is not in CUR; for per‑prompt detail you can use model invocation logs or request metadata tagging.
- Tags appear in CUR 2.0 with the `iamPrincipal/` prefix and are filterable dimensions in Cost Explorer.

## ⚙️ Configuration
- Enable AWS IAM Identity Center in the management (payer) account.
- Connect an external identity provider (Okta, Microsoft Entra ID, or Ping Identity) with SCIM provisioning.
- Configure AWS CLI v2 on developer machines.
- Enable CUR 2.0 with IAM principal data and deliver it to an S3 bucket.
- Activate cost allocation tags from the management account.
- Create an Athena table to query CUR 2.0 data.
- Configure the external identity provider as the identity source in AWS IAM Identity Center.

## 📊 Querying spend
- CUR aggregates usage per principal and per usage type per export interval.
- For finer granularity, per‑request metadata tagging provides token‑level detail in model invocation logs.
- With Application Inference Profiles you can tag spend by workload on the `bedrock-runtime` endpoint.
- With Projects and Workspaces you can isolate and tag spend on the `bedrock-mantle` endpoint.
- In Cost Explorer, filter by `iamPrincipal/` tags to see per‑user spend alongside dollars.

## 📚 Integration with Claude platforms
- Tools such as Claude Code, Claude Desktop, OpenAI Codex, ChatGPT Work, and OpenCode invoke Bedrock via the two endpoints and inherit the same attribution.
- Claude Platform on AWS routes inference through Anthropic‑managed infrastructure; usage is visible by workspace and API key in Anthropic’s admin console, and workspace tags flow to AWS billing.
- Claude for Enterprise also shows per‑user usage in Anthropic’s admin console and its Usage and Cost API, with spend limits enforced natively by Anthropic.

## 💡 Why it matters
- Provides per‑user cost visibility without any code changes.
- Supports four access patterns: IAM users, per‑application roles, federated identities, and LLM gateways proxying to Bedrock.
- Enables organizations to allocate AI spend accurately across teams, projects, and workloads while staying within the AWS security boundary.

#AWS #AmazonBedrock #CostManagement #IAM

---

*Source: [Cost attribution and controls for AI developer and productivity tools on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/cost-attribution-and-controls-for-ai-developer-and-productivity-tools-on-amazon-bedrock/)*
