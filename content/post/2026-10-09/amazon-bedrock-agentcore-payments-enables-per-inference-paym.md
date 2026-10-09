---
title: "Amazon Bedrock AgentCore Payments Enables Per‑Inference Payments for Autonomous Agents"
slug: "amazon-bedrock-agentcore-payments-enables-perinference-payments-for-autonomous-agents"
description: "When an autonomous AI agent needs to buy a service – a model inference, an API response, or web access – those purchases are tiny, frequent, and happen inside the agent’s loop without a human to..."
date: 2026-10-09T18:05:31+05:30
tags: [AmazonBedrock, AIagents, Payments, x402, Stablecoin]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Cloud Computing", "Payments"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21707-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Payments Enables Per‑Inference Payments for Autonomous Agents

When an autonomous AI agent needs to buy a service – a model inference, an API response, or web access – those purchases are tiny, frequent, and happen inside the agent’s loop without a human to approve each one. Amazon Bedrock AgentCore Payments removes that bottleneck by giving agents a managed, spend‑limit‑enforced way to pay for services on demand.

## 🔍 Overview
- Agents often make **hundreds of small purchases** in a single session, each worth a **fraction of a cent**.
- Building a custom payment rail requires solving **wallet management, transaction signing, protocol support, and overspend protection**.
- AgentCore Payments provides a **managed capability** that handles these concerns in just a few lines of code.

## 🧩 How It Works
1. **AgentCore runs the agent** (any framework or model).  
2. **BlockRun acts as the seller**, providing metered model inference via an x402‑compatible endpoint. Each call is quoted, paid, and settled individually.
3. **AgentCore Payments connects to the agent’s wallet** (e.g., a Coinbase CDP‑provisioned wallet) and:
   - Detects an HTTP 402 *Payment Required* response.
   - Signs the transaction with the configured wallet.
   - Returns cryptographic proof to the merchant.
   - Enforces a **spending ceiling** set at the infrastructure layer.
4. Payments settle in a **stablecoin (USDC on the Base network)** and are verifiable on‑chain.

## ⚙️ Key Details
- **Managed wallets** – Incarna provisions each agent’s wallet via the Coinbase CDP connector.
- **Native protocol handling** – AgentCore Payments works with any x402‑compatible endpoint, including Amazon Bedrock inference endpoints.
- **Spending limits** – Limits are enforced by the infrastructure, not by the model, preventing overspend.
- **Payment schemes** – Supports two x402 schemes: **exact** and **upto**; a session sets a ceiling that the agent cannot exceed.
- **Time savings** – The Incarna team reduced the effort to add x402 payment support from **months to days** and launched an end‑to‑end pay‑per‑inference flow in production.
- **Integration steps** – Use the AgentCore payments skill in the Agent Toolkit for AWS to store payment credentials (Coinbase CDP or Stripe Privy) in AWS Secrets Manager, create a Payment Manager, and set a default spending limit.

## 🚀 Availability
AgentCore Payments is a **managed capability of Amazon Bedrock AgentCore** and can be enabled through a guided conversation with the AgentCore payments skill. It works with any framework or model that can call x402‑compatible endpoints.

## 💡 Why It Matters
- **Automation at scale** – Enables autonomous agents to purchase needed services without human intervention.
- **Financial control** – Infrastructure‑level spending caps protect budgets while allowing high‑frequency, low‑value transactions.
- **Simplified development** – Teams can focus on agent logic instead of building and securing custom payment infrastructure.
- **Auditable transactions** – On‑chain settlement in USDC provides transparent, verifiable payment records.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/21707-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21707-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21707-3.jpg)

#AmazonBedrock #AIagents #Payments #x402 #Stablecoin

---

*Source: [Pay-per-inference for AI agents: How BlockRun and Incarna use Amazon Bedrock AgentCore payments | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/pay-per-inference-for-ai-agents-how-blockrun-and-incarna-use-amazon-bedrock-agentcore-payments/)*
