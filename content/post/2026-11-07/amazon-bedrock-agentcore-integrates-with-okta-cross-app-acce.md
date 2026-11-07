---
title: "Amazon Bedrock AgentCore Integrates with Okta Cross App Access for Secure Agent Governance"
slug: "amazon-bedrock-agentcore-integrates-with-okta-cross-app-access-for-secure-agent-governance"
description: "Amazon Bedrock AgentCore is a platform to build, connect, and optimize agents at scale using any framework or model. A new integration with Okta Cross App Access (XAA) allows organizations to manage..."
date: 2026-11-07T06:05:49+05:30
tags: [AWS, AmazonBedrock, Okta, AIagents, Cybersecurity]
categories: ["AI", "AI Agents", "Cloud Security", "Identity Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Integrates with Okta Cross App Access for Secure Agent Governance

Amazon Bedrock AgentCore is a platform to build, connect, and optimize agents at scale using any framework or model. A new integration with Okta Cross App Access (XAA) allows organizations to manage agent identity and governance directly within their identity provider (IdP).

## 🔍 Overview

This solution establishes a clear separation between governance and execution. Okta serves as the governance plane, deciding which agent may act for which user against specific resources. Amazon Bedrock AgentCore serves as the execution plane, managing credentials and turning governance decisions into valid access tokens.

| Component | Role |
| :--- | :--- |
| Okta | Governance plane: decides which agent acts for which user against which resource. |
| Amazon Bedrock AgentCore Identity | Execution plane: holds credentials and redeems grants for tokens in a vault. |
| Amazon Bedrock AgentCore runtime | Validates Okta’s grant. |

## 🧩 How it works

The identity flow ensures that agent actions are always tied to a verified user session:

*   **User Sign-in:** Users access a backend for frontend (BFF) using OpenID Connect via the agent’s linked Okta app.
*   **Token Exchange:** For each request, the BFF performs an RFC 8693 token exchange, trading the user's ID token for an Identity Assertion JWT Authorization Grant (ID-JAG) at Okta’s authorization server.
*   **Okta Verification:** Okta checks that the agent is active, the user is assigned to it, and an administrator has approved the applications and scopes the agent might reach.
*   **Execution:** The BFF invokes the agent on the AgentCore runtime using the ID-JAG. AgentCore Identity then redeems the ID-JAG for a short-lived access token accepted by the resource.

## ⚙️ Key details

The system utilizes three distinct tokens to record different decisions throughout the request lifecycle:

*   **ID Token:** Identifies the user.
*   **Identity Assertion JWT Authorization Grant (ID-JAG):** Represents Okta’s decision; single-use and expires in 5 minutes.
*   **Access Token:** Issued by Okta’s custom authorization server, naming both the user and the agent.

In testing, the governance process proved highly responsive. When an administrator removed a user’s assignment, Okta refused new agent requests for that user within approximately 1 second. Existing tokens expired within 5 minutes. Performance testing showed that AgentCore Identity added roughly 0.6 seconds of latency to a request taking 30 seconds end to end.

## 🚀 Availability

Amazon Bedrock AgentCore charges based on usage. A technical walkthrough for building a task agent with this governance model takes about 1 hour. The associated sample code is provided for non-production use, and organizations should consult with security and legal teams before deployment.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-3.png)

#AWS #AmazonBedrock #Okta #AIagents #Cybersecurity

---

*Source: [Govern AI agent access with Okta Cross App Access and Amazon Bedrock AgentCore – Part 1 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/govern-ai-agent-access-with-okta-cross-app-access-and-amazon-bedrock-agentcore-part-1/)*
