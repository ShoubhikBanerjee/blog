---
title: "Amazon Quick resource migration automated with Bedrock AgentCore MCP server"
slug: "amazon-quick-resource-migration-automated-with-bedrock-agentcore-mcp-server"
description: "Amazon Quick is Amazon’s agentic AI companion built for work.  Moving its resources – chat agents, action connectors, knowledge bases, flows, and spaces – from a development AWS account to a..."
date: 2026-10-05T22:07:36+05:30
tags: [AmazonQuick, Bedrock, MCP, AIautomation]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Developer Tools", "Enterprise AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21611-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Quick resource migration automated with Bedrock AgentCore MCP server

Amazon Quick is Amazon’s agentic AI companion built for work.  Moving its resources – chat agents, action connectors, knowledge bases, flows, and spaces – from a development AWS account to a production account has traditionally been a manual, error‑prone chore.

## 🔍 Overview
- Enterprises often run separate AWS accounts for development, QA, and production.
- There is no native one‑click way to promote validated Quick resources into the next account; teams must rebuild each resource by hand.
- The Quick Resource Migrator is a sample Model Context Protocol (MCP) server hosted on Amazon Bedrock AgentCore that automates this cross‑account promotion with a single tool call.

## 🛠️ How it works
- The migrator composes the **Create**, **Read**, **Update**, and **List** API calls of the Amazon Quick API into a repeatable workflow; it never issues a delete, so a run only adds or updates.
- It is **resource‑driven** – you pick a resource type (agent, connector, knowledge base, flow, or space) and select resources by ID, name, or all.
- The server runs on Amazon Bedrock AgentCore runtime and can be triggered from Amazon Quick or any MCP‑compatible client.

| Resource Type | Migration actions |
|----------------|--------------------|
| Chat agents | Recreate with custom instructions, identity, tone, starter prompts, welcome message; re‑attach action connectors (remapped to target). |
| Action connectors | Recreate configuration; secret values never read – placeholders are created then re‑authenticated in target. |
| Knowledge bases | Register in target, recreate data source, copy permissions; for S3‑backed bases also provision target bucket and bucket policy (documents are not copied). |
| Flows | Recreate from definition; matched by name – same‑named flow is updated, otherwise a new flow is created. |
| Spaces | Recreate in target and re‑link to agents, connectors, and knowledge bases with ARN remapping; agents are automatically re‑linked when a space migrates. |

## ⚙️ Key features
- **Idempotent** – safe to re‑run; performs upserts (creates missing resources, updates existing ones).
- **Permission fidelity** – calls `Describe*Permissions` on the source and replays identical actions in the target, remapping ARNs.
- **Versioned backup** – every update is preceded by a backup written to Amazon S3, giving a full history for review or rollback.
- **Read‑only preview** – reports exactly what would be created or updated before committing.
- **Single‑call promotion** – a chosen set of resources is promoted in one operation.
- **Programmable** – all resources are managed through the Amazon Quick API (full CRUDL lifecycle).
- **Open source** – full source code is available in the `aws-samples` repository.

## 🚀 Availability
- The MCP server is hosted on Amazon Bedrock AgentCore runtime.
- It can be invoked from Amazon Quick or any client that supports MCP.
- Source code and deployment instructions are published in the public `aws-samples` GitHub repository.

## 💡 Why it matters
- Enterprises with separate development and production AWS accounts can eliminate a manual, error‑prone promotion process.
- Consistent permission copying and versioned backups reduce risk of misconfiguration in production.
- Idempotent upserts and preview mode enable safe, repeatable migrations, supporting CI/CD pipelines and governance.
- By automating promotion, teams can focus on building and evaluating agentic AI solutions rather than on repetitive infrastructure work.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/Figure-1-8.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/Figure-2-8.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/Figure-3-3.png)

#AmazonQuick #Bedrock #MCP #AIautomation

---

*Source: [Making Amazon Quick enterprise-ready: Automated, auditable cross-account resource promotion | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/making-amazon-quick-enterprise-ready-automated-auditable-cross-account-resource-promotion/)*
*Source: [Evaluating multi-agent systems for explainability and helpfulness with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/evaluating-multi-agent-systems-for-explainability-and-helpfulness-with-amazon-bedrock-agentcore/)*
