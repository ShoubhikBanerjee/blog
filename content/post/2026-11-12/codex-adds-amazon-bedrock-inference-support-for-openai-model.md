---
title: "Codex adds Amazon Bedrock inference support for OpenAI models"
slug: "codex-adds-amazon-bedrock-inference-support-for-openai-models"
description: "Codex can now invoke supported OpenAI models on Amazon Bedrock while the Codex engine continues to run on the developer’s workstation."
date: 2026-11-12T12:01:25+05:30
tags: [Codex, AmazonBedrock, OpenAI, AIInference]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Developer Tools"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21633-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Codex adds Amazon Bedrock inference support for OpenAI models

Codex can now invoke supported OpenAI models on Amazon Bedrock while the Codex engine continues to run on the developer’s workstation.

## 🔍 Overview
- Codex runs locally on the workstation.
- Inference is performed by Amazon Bedrock using supported OpenAI models such as GPT‑5.6 Sol.
- The pilot uses the open‑source Guidance for Codex on AWS repository.

## 🧩 How it works
- Authentication flow: Okta provides SAML authentication and provisions users/groups to IAM Identity Center via SCIM. IAM Identity Center issues temporary AWS credentials that Codex uses.
- The identity provider is not configured inside Codex.
- Users sign in with an IAM Identity Center profile configured for the AWS CLI, call Amazon Bedrock Runtime directly, then point Codex to the approved model and run a safe task.
- The direct runtime call isolates AWS access problems and creates a short‑lived AWS session that validates model invocation in the selected Region.
- Settings are kept in user‑level or managed configuration so a repository cannot change the provider.

## ⚙️ Key details
- **Quick‑start options** include Native AWS Access, AgentCore Gateway, LiteLLM on ECS, Portkey, ADOT, and Amazon CloudWatch setup.
- Native AWS Access is the default when AWS identity and IAM controls are sufficient.
- AgentCore Gateway is chosen when teams need AWS‑managed gateway infrastructure for routing or Bedrock Guardrails.
- A large language model (LLM) Gateway is used by organizations that already operate a gateway or want request‑path controls.
- Pilot preparation steps:
  - Review Supported models by AWS Region to ensure Sol, Terra, or Luna are available.
  - Choose an Amazon Bedrock Region and an OpenAI model that the pilot identity can access; include an inference profile if required.
  - Grant only the Bedrock model inference permissions needed by Codex plus any validation commands and the selected observability destination.
  - Prepare a non‑production repository and designate a rollback owner.
  - Add each pilot user to a dedicated group in the workforce identity system and provision that group to IAM Identity Center.

## 🚀 Availability
- Before starting, check that the desired model (Sol, Terra, Luna) is listed for the chosen account, Region, and inference path.
- The model identifier used by Codex is the Codex model ID.
- The AWS profile selects the IAM Identity Center session; the Region setting tells Codex which AWS Region to use.

## 💡 Why it matters
- Teams can keep development code on local workstations while leveraging Bedrock’s managed inference and guardrail capabilities.
- Managed gateway options (AgentCore Gateway) simplify routing and security controls without custom infrastructure.
- Using IAM Identity Center and temporary credentials reduces long‑term credential exposure.

| Gateway Type | Intended Use |
|---|---|
| AgentCore Gateway | Fits teams that want AWS managed gateway infrastructure for routing, Amazon Bedrock Guardrails, or related controls |
| LLM Gateway | Fits organizations that already operate a gateway or want to enforce controls in the request path |


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21633-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21633-3.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21633-5.png)

#Codex #AmazonBedrock #OpenAI #AIInference

---

*Source: [OpenAI Codex on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/openai-codex-on-amazon-bedrock/)*
