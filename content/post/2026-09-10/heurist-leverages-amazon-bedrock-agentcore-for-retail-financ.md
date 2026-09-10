---
title: "Heurist leverages Amazon Bedrock AgentCore for retail financial intelligence"
slug: "heurist-leverages-amazon-bedrock-agentcore-for-retail-financial-intelligence"
description: "Heurist is using Amazon Bedrock AgentCore to develop AI-powered financial intelligence for retail investors through its flagship product, Heurist Finance."
date: 2026-09-10T12:09:25+05:30
tags: [AmazonBedrock, Heurist, FinancialAI, AIAgents, FinTech]
categories: ["AI", "AI Agents", "Financial Technology", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/27/ML-21623-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Heurist leverages Amazon Bedrock AgentCore for retail financial intelligence

Heurist is using Amazon Bedrock AgentCore to develop AI-powered financial intelligence for retail investors through its flagship product, Heurist Finance.

## 🔍 Overview
Heurist Finance aims to make institutional-style tools accessible to anyone with a market question. Its capabilities include:

* Gathering market data, news, and filings
* Conducting deep research
* Building and stress-testing portfolios
* Monitoring positions
* Providing unified risk-and-return views and scenario analysis
* Providing access to premium macroeconomic, fundamental, alternative, and market data

## 🧩 How it works
Heurist deployed its agents on Amazon Bedrock AgentCore, using Anthropic Claude (available on Amazon Bedrock) and the Strands orchestrator. The system architecture integrates several AWS and external services:

* **Data Storage:** Portfolio data is loaded from Amazon Aurora PostgreSQL, analysis artifacts are stored in Amazon Simple Storage Service (Amazon S3), and traces are sent to Amazon CloudWatch.
* **Security:** Credentials are kept in AWS Secrets Manager.
* **Infrastructure:** Agents are built, connected, and optimized at scale via AgentCore.

## ⚙️ Key details
Heurist utilizes several specific capabilities of Amazon Bedrock AgentCore:

| Feature | Function |
| :--- | :--- |
| AgentCore payments | Enables buying premium data per query via USDC stablecoin settlement on the Base blockchain network. |
| AgentCore Code Interpreter | Performs analysis in an isolated sandbox in the AWS Cloud with no arbitrary network egress, which tears down after analysis. |
| AgentCore memory | Stores conversation history, thesis state, and user preferences across sessions. |
| AgentCore Identity | Scopes stores to individual users via OAuth and carries authenticated users through service calls, removing the need for a separate access-control layer. |

### Payment Process
Heurist Finance uses a Payment Manager and a CoinbaseCDP Payment Connector following the x402 protocol:
1. Heurist Finance requests a paid data feed from a merchant.
2. The merchant returns an HTTP 402 with payment terms (amount, recipient, USDC asset, and Base network).
3. AgentCore payments verifies the payload against the Payment Session's `maxSpendAmount`.
4. Heurist Finance calls the Process Payment API to sign the payment using a Payment Instrument (embedded crypto wallet scoped to Base).
5. Heurist Finance retries the request with proof in the `X-PAYMENT` header to receive the data.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/27/ML-21623-1.png)

#AmazonBedrock #Heurist #FinancialAI #AIAgents #FinTech

---

*Source: [How Heurist Finance built an AI-native investment workbench on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-heurist-finance-built-an-ai-native-investment-workbench-on-amazon-bedrock-agentcore/)*
