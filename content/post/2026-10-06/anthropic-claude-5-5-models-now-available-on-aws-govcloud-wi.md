---
title: "Anthropic Claude 5.5 Models Now Available on AWS GovCloud with Full Compliance"
slug: "anthropic-claude-5-5-models-now-available-on-aws-govcloud-with-full-compliance"
description: "Anthropic’s latest Claude models—Opus 5.5 and Sonnet 5.5—are now offered through Amazon Bedrock in the U.S. GovCloud regions, giving regulated workloads a compliant path for AI‑assisted development."
date: 2026-10-06T18:04:10+05:30
tags: [AWS, Anthropic, AICompliance, DeveloperTools]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Developer Tools", "Security & Compliance"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-19466-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic Claude 5.5 Models Now Available on AWS GovCloud with Full Compliance

Anthropic’s latest Claude models—Opus 5.5 and Sonnet 5.5—are now offered through Amazon Bedrock in the U.S. GovCloud regions, giving regulated workloads a compliant path for AI‑assisted development.

## 🔍 Overview
- Claude Opus 5.5 and Claude Sonnet 5.5 are available in AWS GovCloud (US‑West and US‑East).
- The models are hosted on Amazon Bedrock, which provides built‑in data protection: customer content is not stored, logged, or used to train AWS models, nor shared with third parties.
- FedRAMP Class D (formerly High) certification and DoD Impact Level 4/5 (IL4/IL5) authorizations are available for these models, satisfying common government compliance requirements.
- AWS GovCloud (US) Regions are purpose‑built for U.S. customers with elevated compliance needs, including ITAR‑restricted workloads.

## 🛠️ How it works
- **Endpoints**: Amazon Bedrock in GovCloud supports two endpoint surfaces:
  - `bedrock-runtime` – accessed via the AWS SDK (InvokeModel and Converse APIs). It supports Guardrails, Knowledge Bases, Agents, and invocation logging, making it the recommended choice for applications that need audit trails.
  - `bedrock-mantle` – implements the Anthropic Messages API natively and adds capabilities such as server‑side tools, background inference, and Projects.
- **Claude Code**: An agentic coding tool powered by Opus 5.5 and Sonnet 5.5. It runs in terminals, IDEs (VS Code, JetBrains), or background via the Claude Agent SDK.
  - Reads the entire codebase, edits files, runs commands, and integrates with CI/CD pipelines (GitHub Actions, GitLab CI/CD).
  - Connects to external tools via the Model Context Protocol (AWS CLI, Terraform, Kubernetes).
  - Can spawn sub‑agents, use CLAUDE.md memory files, and apply custom skills and hooks.

## ⚙️ Key details
- **Compliance**:
  - FedRAMP Class D certification for the models on Bedrock.
  - DoD Cloud Service Provider SRG IL4/IL5 authorization pathways.
  - Integration with existing security controls and compliance frameworks in AWS GovCloud (US).
- **Data protection**: Customer content is never stored, logged, or used for model training, and it is not shared with third parties.
- **Permissions**:
  - `bedrock-runtime` requires `bedrock:InvokeModel`, `bedrock:InvokeModelWithResponseStream`, `bedrock:ListInferenceProfiles`, and `bedrock:GetInferenceProfile`.
  - `bedrock-mantle` requires `bedrock-mantle:CreateInference`, `bedrock-mantle:GetProject`, `bedrock-mantle:ListProjects`, `bedrock-mantle:ListModels` (or the managed policy `AmazonBedrockMantleInferenceAccess`).
- **Access requirements**: An AWS GovCloud (US) account with Amazon Bedrock enabled, appropriate IAM roles, and AWS CLI configured with valid short‑term API keys or AWS SSO login.

## 📦 Availability
| Endpoint | Supported Models | Available Regions | Notable Features |
|-----------|------------------|-------------------|------------------|
| `bedrock‑runtime` | Claude Opus 5.5, Claude Sonnet 5.5, Claude Sonnet 5 | US‑West, US‑East | Uses AWS SDK APIs, supports Guardrails, Knowledge Bases, Agents, invocation logging |
| `bedrock‑mantle` | Claude Opus 5.5, Claude Sonnet 5.5, Claude Sonnet 5 | US‑West only | Native Anthropic Messages API, server‑side tools, background inference, Projects |

## 💡 Why it matters
- Enables generative AI workloads in highly regulated environments without sacrificing compliance.
- Provides government agencies and contractors a FedRAMP‑ and DoD‑authorized path to use state‑of‑the‑art LLMs.
- Claude Code brings AI‑assisted development directly into secure, GovCloud‑hosted pipelines, supporting tasks such as multi‑file bug fixes, architecture queries, Git operations, and automated CI/CD.
- The dual‑endpoint design lets developers choose between audit‑friendly runtime calls and richer feature sets via the Mantle surface.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-19466-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-19466-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-19466-3.jpg)

#AWS #Anthropic #AICompliance #DeveloperTools

---

*Source: [Supercharge regulated workloads with Claude Code and Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/supercharge-regulated-workloads-with-claude-code-and-amazon-bedrock/)*
