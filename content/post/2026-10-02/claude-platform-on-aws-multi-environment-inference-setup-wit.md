---
title: "Claude Platform on AWS: Multi‑environment Inference Setup with Cross‑Account Roles"
slug: "claude-platform-on-aws-multienvironment-inference-setup-with-crossaccount-roles"
description: "Claude Platform on AWS (CPonAWS) now supports a unified subscription that can serve production workloads, developer laptops, and external services across different cloud or on‑prem environments."
date: 2026-10-02T22:04:29+05:30
tags: [ClaudePlatform, AWS, AIInference, CrossAccount]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/21/ML-21203-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Claude Platform on AWS: Multi‑environment Inference Setup with Cross‑Account Roles

Claude Platform on AWS (CPonAWS) now supports a unified subscription that can serve production workloads, developer laptops, and external services across different cloud or on‑prem environments.

## 🔍 Overview
- Inference is needed from three environments: production workloads on AWS, developer laptops for local iteration, and external services on other cloud providers or on‑prem CI/CD pipelines.
- All environments share a single CPonAWS subscription while keeping production and development traffic isolated at the workspace level.

## 🏗️ Architecture
The recommended structure uses three AWS accounts:
1. **Payer (management) account** – handles billing and governance.
2. **AI Services account** – holds the CPonAWS subscription, workspaces, API keys, and cross‑account roles.
3. **Workload accounts** – assume roles in the AI Services account to make inference calls; they never touch the subscription directly.

### Access Patterns
| Access Pattern | Authentication Method | Key Characteristics |
|---|---|---|
| AWS workload accounts | Cross‑account SigV4 | Pods in Amazon EKS assume a role in the AI Services account and make SigV4‑signed inference calls. No API keys are stored and no secrets need rotation. |
| Developer laptops | Workspace‑scoped API key | Long‑lived API key locked to a development workspace; used locally with the standard Anthropic SDK. |
| External workloads | OIDC federation with short‑term keys | Workloads outside AWS authenticate via OIDC, obtain temporary AWS credentials, generate a short‑lived token, and call inference with zero persistent credentials. |

## ⚙️ Step‑by‑Step Setup
- Deploy a dedicated **AI Services account** within your organization and configure cross‑account SigV4 for AWS workloads.
- Generate **workspace‑scoped API keys** for developers.
- Wire up **OIDC federation** for external environments.
- Use AWS CLI v2 with named profiles for both the payer and AI Services accounts.
- Follow the *Introducing Claude Platform on AWS* guide to subscribe the AI Services account to CPonAWS.
- Every step includes a CLI command, console instruction, or code snippet.

## 📦 Workspaces
1. Open the AWS Management Console on the AI Services account and navigate to **Claude Platform on AWS**.
2. In the Claude Console, select the drop‑down menu top‑left and choose **Create Workspace**.
3. Create a workspace named **production** and record its ARN (e.g., `wrkspc_PROD`).
4. Repeat to create a workspace named **development** (e.g., `wrkspc_DEV`). Record both ARNs.
5. Workspaces are region‑specific; API calls must target the matching regional endpoint (e.g., `aws-external-anthropic.us-east-1.api.aws`). The workspace region determines the API endpoint, not the inference location.

## 🚀 Why It Matters
- Centralized subscription reduces management overhead while preserving isolation.
- Cross‑account roles eliminate the need for long‑lived API keys in production workloads.
- OIDC federation enables secure, short‑lived credentials for external services.
- The pattern scales to additional teams or workloads by creating a workspace per team and repeating the role pattern.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/21/ML-21203-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/21/ML-21203-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/21/ML-21203-3.png)

#ClaudePlatform #AWS #AIInference #CrossAccount

---

*Source: [Implementing Multi-Environment Access for Claude Platform on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/implementing-multi-environment-access-for-claude-platform-on-aws/)*
