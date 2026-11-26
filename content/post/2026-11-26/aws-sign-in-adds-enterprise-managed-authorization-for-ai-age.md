---
title: "AWS Sign-In Adds Enterprise-Managed Authorization for AI Agents via ID-JAG"
slug: "aws-sign-in-adds-enterprise-managed-authorization-for-ai-agents-via-id-jag"
description: "AWS Sign‑In is adding Enterprise‑Managed Authorization (EMA) that lets organizations authorize AI agents such as Claude to access AWS MCP Server using existing enterprise identity providers like Okta."
date: 2026-11-26T12:19:42+05:30
tags: [AWS, AIAgents, EnterpriseAuthorization, Okta, OAuth]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Security", "Identity Management"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/Secure-Agentic-Access-to-AWS-4.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Sign-In Adds Enterprise-Managed Authorization for AI Agents via ID-JAG

AWS Sign‑In is adding Enterprise‑Managed Authorization (EMA) that lets organizations authorize AI agents such as Claude to access AWS MCP Server using existing enterprise identity providers like Okta.

## 🔍 Overview
- EMA extends the Model Context Protocol (MCP) to let enterprises centrally control AI‑application access to protected resources.
- It uses the Identity Assertion JWT Authorization Grant (ID‑JAG), an OAuth‑based grant that works with enterprise IdPs.

## 🧩 How it works
1. **Employee authentication** – The employee signs in to an AI application (e.g., Claude) through single sign‑on (SSO) with an enterprise IdP such as Okta.
2. **ID‑JAG request** – When the AI application needs to call an AWS MCP Server, it asks the IdP for an ID‑JAG assertion for the target resource.
3. **Enterprise authorization** – The IdP evaluates policies defined by administrators and, if authorized, issues a short‑lived, signed ID‑JAG assertion.
4. **Token exchange with AWS Sign‑In** – The AI application sends the ID‑JAG to the AWS Sign‑In OAuth token endpoint. AWS validates the assertion, checks the associated IAM role trust policy via AWS STS, and issues an OAuth access token linked to that role.
5. **Access AWS MCP Server** – The AI application presents the OAuth token to the AWS MCP Server. The server validates the token, and the IAM role’s policies determine which AWS operations the agent may perform.

## ⚙️ Key details
- **No extra credentials** – Employees do not need to manage long‑term AWS credentials or complete separate consent flows.
- **Policy‑driven** – Administrators define access rules in the IdP, eliminating per‑user authorizations for each MCP server.
- **IAM enforcement** – After token issuance, standard IAM role permissions control the actions the AI agent can perform on AWS resources.
- **Short‑lived assertions** – ID‑JAG tokens are short‑lived and signed, limiting exposure if compromised.

## 🛠️ Prerequisites
- An AWS account with permission to configure IAM identity providers, roles, and policies.
- An Okta organization with administrative rights to manage applications and Cross‑App Access policies.
- An AI application (e.g., Claude) that supports EMA and ID‑JAG.
- Access to an AWS MCP Server that supports OAuth‑based Enterprise‑Managed Authorization.
- The AWS Region where the integration will be configured.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure-1-enterprise-managed-authorization-flow-using-okta-aws-sign-in-and-aws-mcp-server.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure-2-creating-the-claude-sso-app-integration-in-okta.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure-3-adding-okta-as-an-openid-connect-identity-provider-in-iam.png)

#AWS #AIAgents #EnterpriseAuthorization #Okta #OAuth

---

*Source: [Secure agentic access to AWS with Enterprise-Managed Authorization | Amazon Web Services](https://aws.amazon.com/blogs/security/secure-agentic-access-to-aws-with-enterprise-managed-authorization/)*
