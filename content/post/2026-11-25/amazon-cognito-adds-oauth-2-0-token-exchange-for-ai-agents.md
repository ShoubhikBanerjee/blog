---
title: "Amazon Cognito adds OAuth 2.0 token exchange for AI agents"
slug: "amazon-cognito-adds-oauth-2-0-token-exchange-for-ai-agents"
description: "Amazon Cognito introduces a new OAuth token exchange feature that enables services and AI agents to call APIs on behalf of users. This functionality aligns with OAuth 2.0 Token Exchange standards..."
date: 2026-11-25T22:10:10+05:30
tags: [AmazonCognito, OAuth20, AIAgents, TokenExchange, Security]
categories: ["AI", "Cloud Security", "AI Agents", "Identity & Access Management", "API Development"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/Token-Exchange-Image.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Cognito adds OAuth 2.0 token exchange for AI agents

Amazon Cognito introduces a new OAuth token exchange feature that enables services and AI agents to call APIs on behalf of users. This functionality aligns with OAuth 2.0 Token Exchange standards defined in RFC 8693, facilitating secure delegation where AI agents select tools at runtime, such as Model Context Protocol (MCP) servers, to perform actions like reserving tables or sending invitations.

## 🔍 Overview
AI agents increasingly interact with various APIs on behalf of users, requiring a mechanism to handle the "second hop" where an intermediate service (like an MCP server) needs to access a downstream resource (like an email API). Without proper token exchange, forwarding the user's original access token is insufficient because it does not clearly identify which service acted on the user's behalf. This new feature allows Cognito to act as the authorization server, issuing new tokens for the calling service while maintaining strict scope controls.

## 🧩 How it works
Every token exchange begins with a **subject token** that represents the user, which in Amazon Cognito can be an access token or ID token issued by a user pool. The calling service, such as an MCP server, sends this subject token to Cognito. 

*   **Request Flow:** The client calls the downstream service with the user's access token. The service then calls the Cognito `/oauth2/token` endpoint, authenticating with its own app client credentials.
*   **Validation:** Cognito validates the request and returns an **issued token**.
*   **Access:** The service uses this issued token to call the resource server (e.g., an email API).
*   **Claim Structure:** The issued token identifies the user and names the calling service via an **act claim**. It carries the same scopes or fewer than the original token, ensuring the downstream API sees exactly which service acted for the user.

## ⚙️ Key details
The feature distinguishes between two authorization patterns:

| Pattern | Use Case | Characteristics |
| :--- | :--- | :--- |
| **Impersonation** | Backend for Frontend (BFF) relaying requests | The calling service relays the user's request without making its own decisions. The record shows the user but not the agent acting. |
| **Delegation** | AI agents acting with autonomy | The agent makes decisions and uses its own tools. The record shows both the user and the agent, which is critical for proper authorization and audit trails. |

For AI agents, delegation is the primary pattern. If an agent used a token of its own without delegation, the audit record would show the agent called the resource server but not *for whom*. Conversely, impersonation hides the agent. Delegation ensures that the **act claim** logs who authorized the action (the user) and who carried it out (the service/agent).

Developers can initiate token exchange in two ways:
*   **HTTP Endpoint:** Requesting a token exchange at the `/oauth2/token` endpoint on the user pool’s domain.
*   **AWS SDK:** Calling the `GetDerivedToken` API, which does not require a user pool domain.
Both methods accept the same subject token, actor token, audience, and scopes, returning an issued token with identical claims.

## 💡 Why it matters
As AI agents become more capable of picking tools at runtime, such as MCP servers that send invitations or manage reservations, the need for granular, auditable access control grows. Token exchange ensures that each hop in the chain receives only the scopes it needs. By identifying the acting service through the act claim, organizations can maintain clear audit trails, ensuring that when an AI agent performs an action like reserving a table or inviting friends, the record clearly associates that action with both the end user and the specific agent or service that executed it.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/figure-1-second-hop.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/cognito-token-exchange-flow-figure-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/figure-5-invitations-mcp-server.png)

#AmazonCognito #OAuth2.0 #AIAgents #TokenExchange #Security

---

*Source: [Delegate user access to AI agents with Amazon Cognito token exchange | Amazon Web Services](https://aws.amazon.com/blogs/security/delegate-user-access-to-ai-agents-with-amazon-cognito-token-exchange/)*
