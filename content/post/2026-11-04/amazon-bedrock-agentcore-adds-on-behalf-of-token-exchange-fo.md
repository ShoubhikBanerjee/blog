---
title: "Amazon Bedrock AgentCore adds on‑behalf‑of token exchange for identity‑preserving API calls"
slug: "amazon-bedrock-agentcore-adds-onbehalfof-token-exchange-for-identitypreserving-api-calls"
description: "AI agents that interact with enterprise APIs must keep the calling user’s identity throughout the request chain. Without identity propagation, downstream services see the request as coming from the..."
date: 2026-11-04T06:03:46+05:30
tags: [AmazonBedrock, AIAgents, OAuth, IdentityPropagation]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Security", "Enterprise Integration"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-21070-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore adds on‑behalf‑of token exchange for identity‑preserving API calls

## 🔍 Overview
AI agents that interact with enterprise APIs must keep the calling user’s identity throughout the request chain. Without identity propagation, downstream services see the request as coming from the application instead of the user, breaking audit trails, bypassing user‑level access controls, and violating the principle of least privilege.

Amazon Bedrock AgentCore is a platform to build, connect, and optimise agents at scale. This update shows how to configure the AgentCore Gateway for an on‑behalf‑of (OBO) token exchange with Microsoft Entra ID so that an AI agent can call the ServiceNow REST API while preserving the user’s identity.

## 🧩 How it works
1. The user acquires a JSON Web Token (JWT) to invoke the agent. *(Figure 1)*
2. The agent authenticates to the gateway with a JWT scoped to the agent’s own application registration.
3. The gateway exchanges that token, using the OBO flow, for a new token scoped to the ServiceNow API connector. The new token retains the original user’s claims.
4. ServiceNow receives a token whose `preferred_username` claim maps to an existing ServiceNow user and applies that user’s permissions to the API call.

Key token details:
- The agent presents a JWT with an audience claim matching the agent’s client ID (e.g., `3ff88e17-XXXX-…`).
- ServiceNow expects a token with an audience claim matching its own API connector client ID (e.g., `5d4a7a11-XXXX-…`).
- The OBO flow bridges this gap.
- AgentCore Gateway sends the inbound token to the Entra token endpoint together with the agent client credentials, the target scope, and `requested_token_use=on_behalf_of`.
- Entra validates the user’s consent to delegation and issues a new token for the ServiceNow API with the original user’s claims intact.

## ⚙️ Configuration steps
- **Prerequisites**
  - A Microsoft Entra ID tenant with permissions to create application registrations (at least the *Application Developer* role).
  - A ServiceNow instance with admin access to configure inbound OAuth integrations (a personal developer instance can be created at the ServiceNow developer site).
- **Create two Entra application registrations**
  1. *ServiceNow API connector* – represents the ServiceNow API connector.
     - After creation, note the Application (client) ID.
     - In **Expose an API**, add a scope named `user_impersonation` using the default Application ID URI. This scope is requested by the OBO flow.
  2. *AI agent* – represents the AI agent.
- **Configure AgentCore Gateway**
  - Define a gateway target for the ServiceNow API.
  - Enable OBO token exchange on the target; AgentCore Gateway will perform the exchange for each request.
- **ServiceNow side**
  - Configure inbound OAuth to accept tokens issued by Entra ID.
  - Ensure the `preferred_username` claim maps to a ServiceNow user.

## 💡 Why it matters
- Maintaining user identity prevents audit‑trail gaps and ensures that downstream services enforce user‑level access controls.
- The pattern can be applied to any REST API protected by OAuth, not just ServiceNow.
- In production you can pair identity propagation with Amazon Bedrock Guardrails to filter harmful content and validate the agent’s inputs and outputs.

## 🚀 Next steps
- Deploy the described configuration in a test environment.
- Extend the OBO pattern to other enterprise APIs.
- Combine with Bedrock Guardrails for comprehensive security and compliance.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-21070-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-21070-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-21070-3.png)

#AmazonBedrock #AIAgents #OAuth #IdentityPropagation

---

*Source: [ServiceNow on-behalf-of token exchange with Bedrock AgentCore Gateway | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/servicenow-on-behalf-of-token-exchange-with-bedrock-agentcore-gateway/)*
