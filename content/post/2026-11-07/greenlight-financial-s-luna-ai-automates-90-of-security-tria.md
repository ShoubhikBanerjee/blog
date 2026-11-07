---
title: "Greenlight Financial’s Luna AI automates 90% of security triage using Amazon Bedrock AgentCore"
slug: "greenlight-financials-luna-ai-automates-90-of-security-triage-using-amazon-bedrock-agentcore"
description: "Greenlight Financial has updated its Luna AI platform to automatically resolve more than 90 % of up to 4,000 security and risk cases each month, relying on Amazon Bedrock AgentCore for the underlying..."
date: 2026-11-07T18:01:21+05:30
tags: [AIagents, SecurityAutomation, AmazonBedrock]
categories: ["AI", "Artificial Intelligence", "Security Operations", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21973-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Greenlight Financial’s Luna AI automates 90% of security triage using Amazon Bedrock AgentCore

Greenlight Financial has updated its Luna AI platform to automatically resolve more than 90 % of up to 4,000 security and risk cases each month, relying on Amazon Bedrock AgentCore for the underlying agent infrastructure.

## 🔍 Overview
- The Security Operations Center (SOC) receives **3,000–4,000 alerts per month** from four primary vectors: dark‑web breach cards, identity and access anomalies, infrastructure alerts, and financial‑risk events.
- Each alert historically required a human analyst **15–30 minutes** to cross‑reference multiple data sources.
- Luna now handles the bulk of triage without human intervention, reducing the median triage time for routine cases to **single‑digit seconds**.

## 🧩 How it works
- Luna is built as a **hierarchical, tiered‑supervisor multi‑agent system** on **Amazon Bedrock AgentCore**.
- **AgentCore runtime** hosts Luna’s agent code; **AgentCore memory** supports the tiered structure, eliminating the need to build these capabilities in‑house.
- **Tier 1 supervisor** runs an advanced language model on Amazon Bedrock within a private VPC, orchestrating **more than 30 specialized agents**.
- Incoming cases reach Tier 1 via two paths:
  - Amazon API Gateway exposing the Luna Queue API and a Model Context Protocol (MCP) endpoint.
  - Tines SOAR for automated alert ingestion.
- Tier 1 determines the appropriate specialized agents, synthesizes findings, and issues a verdict.
- Cases that exceed Tier 1’s confidence threshold are escalated to a **Tier 2 supervisor** that uses an advanced foundation model with extended reasoning capabilities. Tier 2:
  - Invokes specialized agents through **boto3** with expanded context windows.
  - Chains reasoning across **3–5 data sources** to establish causality.
  - Produces detailed investigation reports with evidence chains for human review.
- Different teams can engage Luna through three entry points, ranging from fully automated ingestion to interactive on‑demand investigation.

## ⚙️ Key details
| Alert Vector | What the alert signals |
|--------------|------------------------|
| Dark web breach cards | Card Network and internal threat intel flag Greenlight customer cards found on the dark web |
| Identity and access anomalies | Unusual login patterns, privilege escalations, and policy violations across IdP and internal systems |
| Infrastructure alerts | Signals from EDR, SIEM, Asset Inventory, and other observability tools |
| Financial risk events | Suspicious transaction patterns, compliance triggers, and fraud indicators from card processing systems |

- **AgentCore memory** enables the tiered multi‑agent system.
- The runtime operates in private subnets with code deployed via a ZIP file and Amazon S3.
- Luna triages dark‑web breach‑card alerts, identity anomalies, and financial‑risk events **in seconds**.

## 🚀 Impact
- **>90 %** of up to 4,000 monthly cases are resolved without human input.
- Human analysts are freed from the 15‑30 minute per‑case workflow, allowing focus on the remaining ~10 % of cases that require multi‑step reasoning.
- The architecture mirrors traditional SOC team hierarchies while delivering **single‑digit‑second** median triage times for routine alerts.

## 📡 Integration points
- **Amazon API Gateway**: exposes Luna Queue API and Model Context Protocol endpoint.
- **Tines SOAR**: provides automated alert ingestion.
- **boto3**: used by Tier 2 supervisor to call specialized agents with expanded context.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/c-ml-21973-arch.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21973-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21973-3.jpg)

#AIagents #SecurityAutomation #AmazonBedrock

---

*Source: [How Greenlight Financial built an autonomous SOC solution on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-greenlight-financial-built-an-autonomous-soc-solution-on-amazon-bedrock-agentcore/)*
