---
title: "Adding PKI‑Based Authentication to the Model Context Protocol with Keyfactor EJBCA and AWS"
slug: "adding-pkibased-authentication-to-the-model-context-protocol-with-keyfactor-ejbca-and-aws"
description: "Multi‑agent AI frameworks increasingly use the Model Context Protocol (MCP) to connect agents to external tools and data sources. MCP defines how a large language model (LLM)-powered agent invokes..."
date: 2026-10-20T22:03:21+05:30
tags: [AIAgents, PKI, AWS, MCP]
categories: ["AI", "Artificial Intelligence", "Security", "Cloud Computing", "Machine Identity Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21717-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Adding PKI‑Based Authentication to the Model Context Protocol with Keyfactor EJBCA and AWS

Multi‑agent AI frameworks increasingly use the Model Context Protocol (MCP) to connect agents to external tools and data sources. MCP defines how a large language model (LLM)-powered agent invokes tools such as database queries or email operations, but MCP has no built-in authentication standard. This post shows how to fill that gap using Keyfactor EJBCA together with AWS services.

## 🔍 Overview
- Multi‑agent AI frameworks increasingly use the Model Context Protocol (MCP) to connect agents to external tools and data sources.
- MCP defines how a large language model (LLM)-powered agent invokes tools such as database queries or email operations.
- MCP has no built‑in authentication standard.

## 🛠️ Architecture
The solution combines Keyfactor EJBCA with several AWS managed services and implements three authentication layers that protect each trust boundary in the agent communication chain.

| AWS Service | Role in the architecture |
|------------|--------------------------|
| Amazon Bedrock (via Strands Agents SDK) | LLM inference for agents |
| Amazon RDS for MySQL | Application database accessed through MCP tools |
| Amazon Simple Email Service (SES) | Email delivery for the Email Agent |
| AWS Secrets Manager | Secure storage for PKCS12 bundles, tokens, and metadata |
| Amazon EC2 | Hosts Keycloak identity provider and EJBCA PKI server |

## 🔐 Authentication Layers
1. **Layer 1 – User Auth (User → System)**
   - Uses OAuth together with an X.509 certificate and delegation minting.
   - Provides user identity and credential binding.
2. **Layer 2 – Agent‑to‑Agent (Agent → Agent)**
   - Relies on signed request envelopes containing proof‑of‑possession, a nonce, and a timestamp.
   - Guarantees caller identity, request freshness, and prevents replay.
3. **Layer 3 – MCP Auth (Agent → Tool Server)**
   - Combines a scoped token, the signed envelope, and a delegation assertion.
   - Covers all identities, creates a full authorization chain, and incorporates OCSP validation.

## ⚙️ Key Components & Controls
- **Signed request envelopes** – give cryptographic proof‑of‑possession on every agent call.
- **User‑signed delegation assertions** – authorize agents without sharing credentials.
- **RFC 8693 audience‑scoped tokens** – limit exposure if a token is disclosed.
- **Real‑time OCSP revocation checking** – propagates credential changes instantly across agents.
- **EJBCA Enterprise** – a PKI platform that supports high‑availability deployment, REST API automation, X.509 certificate issuance, OCSP validation, certificate revocation list distribution, and full certificate lifecycle management via web console and REST API.
- **Keyfactor** – a machine‑identity management platform used by more than 1,500 enterprise customers worldwide.

## 🚀 Deployment Options
- EJBCA can be deployed **on‑premises**, in **containers**, or on **Amazon EC2**.
- Designed for **high‑availability** and **REST API automation** to integrate with AWS services.

## 💡 Why it matters
- The added layers supply authentication and authorization that MCP originally lacked.
- Cryptographic proof‑of‑possession, delegations, scoped tokens, and immediate revocation together reduce the risk of credential misuse while preserving the flexibility of multi‑agent AI workflows.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21717-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21717-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21717-3.jpg)

#AIAgents #PKI #AWS #MCP

---

*Source: [Securing AI agent identity with X.509 PKI on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/securing-ai-agent-identity-with-x-509-pki-on-aws/)*
