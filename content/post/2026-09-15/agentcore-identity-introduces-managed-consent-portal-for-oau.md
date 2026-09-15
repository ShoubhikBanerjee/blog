---
title: "AgentCore Identity Introduces Managed Consent Portal for OAuth Session Binding"
slug: "agentcore-identity-introduces-managed-consent-portal-for-oauth-session-binding"
description: "AgentCore Identity, a capability of Amazon Bedrock AgentCore, now offers a Consent portal to provide a managed web experience and session binding endpoint for AgentCore Gateway."
date: 2026-09-15T12:03:19+05:30
tags: [AmazonBedrock, AgentCore, OAuth, AIagents, AWS]
categories: ["AI", "AI Agents", "Cloud Computing", "Cybersecurity"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/14/ML-21874-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AgentCore Identity Introduces Managed Consent Portal for OAuth Session Binding

AgentCore Identity, a capability of Amazon Bedrock AgentCore, now offers a Consent portal to provide a managed web experience and session binding endpoint for AgentCore Gateway.

## 🔍 Overview
AI agents often require access to services like Slack and GitHub on a user's behalf. This requires the user to authenticate with the provider and approve access, while the application securely associates the resulting OAuth grant with that user. Previously, customers using the AgentCore Identity three-legged OAuth (3LO) flow—also known as the OAuth 2.0 authorization code flow—were required to build and host their own session binding infrastructure.

## 🧩 How it works
Administrators create a portal for a gateway and share the URL with users. The process follows these steps:

* Users authenticate via the organization's identity provider (IdP).
* Users review available services and grant consent to individual providers.
* The portal manages browser redirects and session binding.
* AgentCore Identity stores the resulting tokens in its token vault.
* Subsequent tool calls can utilize the stored token without repeated prompts.

## ⚙️ Key details
Configuration involves several technical requirements:

* **Identity Provider (IdP):** An OpenID Connect (OIDC) web application must be created for the portal with the authorization code grant enabled. The IdP must issue a JSON Web Token (JWT) access token for portal validation.
* **Credential Management:** The portal reads the IdP client ID and secret from an OAuth2 credential provider. GitHub and Slack client secrets are stored in AWS Secrets Manager.
* **Permissions:** An AWS Identity and Access Management (IAM) statement covers the "Create default role" option, creating a service role named `AmazonBedrockAgentCoreConsentPortalDefaultServiceRole-<suffix>`.
* **OAuth Connectivity:** AgentCore Identity utilizes separate outbound OAuth credential providers for GitHub and Slack, with callback URLs registered to the matching provider applications.

## 💡 Why it matters
This capability is specifically useful for agents accessed through Model Context Protocol (MCP) clients and IDEs, including:

* Cursor
* Visual Studio Code
* Claude Code
* Kiro

#AmazonBedrock #AgentCore #OAuth #AIagents #AWS

---

*Source: [Manage end-user OAuth consent for AI agents with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/manage-end-user-oauth-consent-for-ai-agents-with-amazon-bedrock-agentcore/)*
