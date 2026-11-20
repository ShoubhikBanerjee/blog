---
title: "Amazon Bedrock AgentCore Extends Autonomy to AWS Marketplace"
slug: "amazon-bedrock-agentcore-extends-autonomy-to-aws-marketplace"
description: "Amazon Bedrock AgentCore payments has been updated to extend agent autonomy to AWS Marketplace, allowing agents to discover and buy x402-enabled software, APIs, data, and content while paying in USD..."
date: 2026-11-20T12:08:10+05:30
tags: [AWS, AmazonBedrock, AgenticCommerce, CloudComputing]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Enterprise Software"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22459-featured-image-2.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Extends Autonomy to AWS Marketplace

Amazon Bedrock AgentCore payments has been updated to extend agent autonomy to AWS Marketplace, allowing agents to discover and buy x402-enabled software, APIs, data, and content while paying in USD on the agent developer's AWS bill.

## 🔍 Overview
- Amazon Bedrock AgentCore payments originally became generally available in August 2026, allowing autonomous payment for paid APIs, MCP servers, and web content over open protocols like x402 and MPP.
- The latest update adds AWS Billing as a payment option, removing the need for stablecoin wallets or API keys.
- AWS is laying the foundation for autonomous commerce at production scale by bringing secure, x402-powered transactions to AWS Marketplace.
- Tavily is collaborating with the AWS team on the design of Agentic Commerce as a trusted, KYC-verified live search provider.

## 🧩 How it works
- **Discover:** Agents call read-only gateway tools in order (search listings, get a listing, list fulfillment options) using the AWS Marketplace connector in AgentCore Gateway.
- **Get a quote:** The agent calls the endpoint with no payment attached, and the seller answers with HTTP 402 and a signed quote in the PAYMENT-REQUIRED header.
- **Pay:** The agent passes the quote to the ProcessPayment API with the payment type AWS_BILLING_X402. AgentCore payments checks session budgets and issues a payment token if funds remain.
- **Redeem:** The agent sends the request again with the payment token in the PAYMENT-SIGNATURE header to receive the content.
- **Settle:** On the first purchase, AWS Marketplace creates an agreement with the seller, and subsequent purchases are metered to the developer's AWS bill monthly.

| Component | Function |
| --- | --- |
| AgentCore Gateway | Provides an optional AWS Marketplace connector to help agents find products and endpoints |
| Payment Manager | Set up by the developer with an AWS Billing connector using a service-linked role |
| AgentCore Policy | Enables developers to set spending limits and approved sellers |

## ⚙️ Key details
- AWS Billing currently supports the x402 exact scheme where the seller quotes a fixed price per request.
- Payment tokens are valid for about five minutes.
- AWS Marketplace checks quote signatures against the seller's registered key to reject altered prices.
- If an organization uses Private Marketplace, agents can only buy allowed products.
- Transactions are auditable in AWS CloudTrail and AWS Cost Explorer.

## 🚀 Availability
- An accompanying GitHub sample is available for developers to evaluate the setup in their own AWS account.
- The x402 catalog on AWS Marketplace is expanding with a growing roster of trusted, verified sellers, including Tavily.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/awsbilling-ecosystem-transparent.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/x402-payment-flow.png)

#AWS #AmazonBedrock #AgenticCommerce #CloudComputing

---

*Source: [Enable AI agents to pay for AWS Marketplace x402 products with Amazon Bedrock AgentCore payments | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/enable-ai-agents-to-pay-for-aws-marketplace-x402-products-with-amazon-bedrock-agentcore-payments/)*
