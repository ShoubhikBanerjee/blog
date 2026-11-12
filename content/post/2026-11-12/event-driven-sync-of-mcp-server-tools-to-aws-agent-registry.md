---
title: "Event‑Driven Sync of MCP Server Tools to AWS Agent Registry"
slug: "eventdriven-sync-of-mcp-server-tools-to-aws-agent-registry"
description: "When a Model Context Protocol (MCP) server published in the AWS Agent Registry gains a new tool or updates its schema, the registry record is automatically refreshed via an event‑driven workflow."
date: 2026-11-12T18:01:15+05:30
tags: [AWS, AgentRegistry, EventBridge, Lambda, MCP]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Serverless Architecture", "DevOps"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21088-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Event‑Driven Sync of MCP Server Tools to AWS Agent Registry

When a Model Context Protocol (MCP) server published in the AWS Agent Registry gains a new tool or updates its schema, the registry record is automatically refreshed via an event‑driven workflow.

## 🔍 Overview
- An MCP server published in the AWS Agent Registry must keep its tool or schema record up‑to‑date.
- An event‑driven workflow uses AWS CloudTrail, Amazon EventBridge, and AWS Lambda to automate the update.
- The solution works in both single‑account and multi‑account environments.

## 🏗️ Architecture
- **AWS CloudTrail** – captures `UpdateAgentRuntime` API calls as management events.
- **Amazon EventBridge** – routes matching events to a Lambda function; supports cross‑account forwarding.
- **AWS Lambda (sync function)** – queries the MCP server, diffs the tool list against the registry, and updates the record when needed.
- **AWS Agent Registry** – stores MCP server records and their tool schemas as the source of truth.
- **AgentCore Identity** – brokers OAuth token exchanges so the Lambda can authenticate without storing secrets.
- **Account roles**
  - *Account A* (registry account) owns the Agent Registry, EventBridge rule, sync Lambda, and CloudTrail logs.
  - *Account B* (MCP server account) hosts the MCP server runtime and the Amazon Cognito OAuth provider.

## ⚙️ How It Works
1. A developer updates an MCP server in Account B; the server calls the `UpdateAgentRuntime` API (via AgentCore CLI or directly).
2. CloudTrail in Account B records the call as a management event (≈ 5–15 min delay).
3. EventBridge in Account B captures the CloudTrail event and forwards it to the default EventBridge bus in Account A (cross‑account rule when applicable).
4. The EventBridge rule in Account A triggers the sync Lambda, passing the full CloudTrail event JSON.
5. The Lambda extracts the runtime Amazon Resource Name (ARN) from the event and builds the MCP server’s invocation URL.
6. The Lambda obtains a secure OAuth bearer token through AgentCore Identity.
7. The Lambda calls the MCP server (`initialize`, then `tools/list`) to retrieve the latest tools information.
8. The Lambda locates the corresponding registry record by ARN, compares the retrieved schema with the stored one, and updates the record if a change is detected.
9. The process assumes the registry already contains a pre‑registered record for the MCP server; the Lambda updates existing records only and does not create new ones.

## 🚀 Availability
- The same workflow runs unchanged in a single‑account deployment where the registry, Lambda, EventBridge rule, and MCP server all reside in Account A.
- In a multi‑account deployment, runtime events flow securely from Account B to Account A before the Lambda performs the sync.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21088-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21088-2-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21088-3-1.jpg)

#AWS #AgentRegistry #EventBridge #Lambda #MCP

---

*Source: [Automating AWS Agent Registry updates with push-based architecture | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/automating-aws-agent-registry-updates-with-push-based-architecture/)*
