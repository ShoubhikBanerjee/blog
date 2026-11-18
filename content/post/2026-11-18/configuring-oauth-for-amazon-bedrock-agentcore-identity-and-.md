---
title: "Configuring OAuth for Amazon Bedrock AgentCore Identity and Snowflake MCP Servers"
slug: "configuring-oauth-for-amazon-bedrock-agentcore-identity-and-snowflake-mcp-servers"
description: "Enterprises extending authentication and authorization controls into the agentic layer often require broad service account permissions or custom-built auth integrations that add operational overhead...."
date: 2026-11-18T06:16:59+05:30
tags: [AmazonBedrock, Snowflake, OAuth, ArtificialIntelligence, Security]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Security"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21095-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Configuring OAuth for Amazon Bedrock AgentCore Identity and Snowflake MCP Servers

Enterprises extending authentication and authorization controls into the agentic layer often require broad service account permissions or custom-built auth integrations that add operational overhead. When an AI agent running on Amazon Bedrock AgentCore needs to call the Snowflake-managed MCP server through the Model Context Protocol, enterprises must determine how the agent authenticates.

## 🔍 Overview

Amazon Bedrock AgentCore Gateway connects AI agents to external tool providers through MCP server targets, targeting the Snowflake-managed MCP server which surfaces Cortex Search and Cortex Analyst as MCP tools. The Gateway aggregates capabilities of its configured targets into a single unified catalog presented to the agent as one tools/list response. The core focus is outbound authentication for Amazon Bedrock AgentCore Gateway, detailing how it obtains and presents OAuth tokens to the Snowflake-managed MCP server.

## ⚙️ Key details

- Amazon Bedrock AgentCore Identity acts as the credential broker, where the Gateway obtains a workload token by calling GetWorkloadAccessTokenForJWT, then calls GetResourceOauth2Token against the configured provider.
- AgentCore Identity owns the token vault, token refresh, and user-to-token binding, automatically fetching, caching, and refreshing tokens.
- AgentCore Identity supports three OAuth configurations spanning two grant types (authorization_code and client_credentials).
- Snowflake OAuth allows Snowflake to act as its own OAuth authorization server with each user authenticating directly through the Authorization Code grant (3LO) without an external IdP.
- Three-legged OAuth uses a third-party Identity Provider where users authenticate through corporate SSO with the Authorization Code grant, and Snowflake trusts IdP-issued JWTs through its External OAuth security integration.
- Two-legged OAuth pattern uses a third-party IdP with a shared service user authenticating through the client_credentials grant, requiring no user interaction or consent, making it ideal for machine-to-machine workloads.
- AgentCore Identity also supports an on-behalf-of (OBO) grant (TOKEN_EXCHANGE) that delivers per-user identity for unattended workloads without a consent prompt.
- An API-key credential provider supports Snowflake Programmatic Access Tokens, though OAuth is focused on for per-user attribution and automatic token refresh.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21095-1-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21095-2-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21095-3-2.png)

#AmazonBedrock #Snowflake #OAuth #ArtificialIntelligence #Security

---

*Source: [Secure OAuth patterns for Snowflake Cortex AI through Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/secure-oauth-patterns-for-snowflake-cortex-ai-through-amazon-bedrock-agentcore/)*
