---
title: "Amazon Bedrock AgentCore adds JWT-secured Claude Desktop web-search integration"
slug: "amazon-bedrock-agentcore-adds-jwt-secured-claude-desktop-web-search-integration"
description: "Amazon Bedrock AgentCore now supports a secure integration that lets Claude Desktop invoke a fully managed web‑search tool via the AgentCore Gateway."
date: 2026-10-02T22:04:29+05:30
tags: [AmazonBedrock, AIAgents, WebSearch, AWSSecurity]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Security"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/30/ML-21694-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore adds JWT-secured Claude Desktop web-search integration

Amazon Bedrock AgentCore now supports a secure integration that lets Claude Desktop invoke a fully managed web‑search tool via the AgentCore Gateway.

## 🔍 Overview
- **AgentCore**: a platform to build, connect, and optimize agents at scale, with any framework or model.
- **AgentCore Gateway**: a capability of AgentCore that can close the knowledge‑cutoff gap by connecting Claude Desktop to Web Search.
- **Web Search**: a fully managed, Model Context Protocol (MCP)‑compatible search service backed by an Amazon index of tens of billions of documents.
- All query traffic stays within AWS infrastructure, with no external API keys and no queries leaving your boundary.

## 🧩 How it works
1. **IAM Identity Center** authenticates the user via SAML.
2. **Amazon Cognito** is registered as a federation layer; it receives the SAML assertion and issues a JSON Web Token (JWT).
3. Claude Desktop uses an app client (with client secret) to start the OAuth 2.0 authorization‑code flow, obtains the JWT, and calls the AgentCore Gateway.
4. The **AgentCore Gateway** validates the JWT on each request and forwards the query to the Web Search target.
5. The entire authentication chain stays within AWS.

## ⚙️ Prerequisites
- An AWS account with permissions to create IAM roles and Bedrock AgentCore resources.
- Admin access in the AWS Organizations management account for IAM Identity Center configuration.
- AWS IAM Identity Center pre‑configured for SSO access to AWS accounts.
- Claude Desktop set up with Amazon Bedrock as the inference provider.
- AWS CLI v2 installed and configured.
- Python 3.10 or later.
- Latest Boto3 SDK.

## 🛠️ Setup steps
1. Verify the target region is **us-east-1**, **eu-west-1**, or **ap-northeast-1** (the only regions where Web Search on AgentCore is available).
2. In the target AWS account, create an Amazon Cognito user pool to act as the OpenID Connect (OIDC) token issuer.
3. In the AWS Organizations management account, create a SAML application that federates with Cognito and assign the users or groups that should access Web Search.
4. Back in the target account, register IAM Identity Center as a SAML identity provider in the Cognito user pool.
5. Create a Cognito app client with a client secret; Claude Desktop will use this client to initiate the OAuth flow.
6. Create a new AgentCore Gateway, set **Inbound Auth Type** to **JSON Web Tokens (JWT)**, and enable the **Web Search** tool.
7. Claude Desktop connects to the AgentCore Gateway using the JWT obtained from Cognito.

## 🚀 Availability
| Region | Identifier |
|--------|------------|
| US East (N. Virginia) | us-east-1 |
| Europe (Ireland) | eu-west-1 |
| Asia Pacific (Tokyo) | ap-northeast-1 |

## 💡 Why it matters
- Enterprises can keep all search queries inside their AWS boundary, eliminating the need to manage external API keys.
- The JWT‑based inbound authentication leverages existing SSO (IAM Identity Center) and federation (Cognito) services, simplifying access control.
- The integration provides a practical way to reduce the knowledge‑cutoff limitation of Claude Desktop by tapping a live web index.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21694-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21694-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-21694-3.png)

#AmazonBedrock #AIAgents #WebSearch #AWSSecurity

---

*Source: [Add secure Web Search to Claude Desktop with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/add-secure-web-search-to-claude-desktop-with-amazon-bedrock-agentcore/)*
