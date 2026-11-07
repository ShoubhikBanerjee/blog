---
title: "Amazon Bedrock AgentCore adds EKS‑run agent with Okta‑driven governance"
slug: "amazon-bedrock-agentcore-adds-eksrun-agent-with-oktadriven-governance"
description: "A second coding agent was added on Amazon Elastic Kubernetes Service (Amazon EKS) and wired through the same Amazon Bedrock AgentCore Gateway. The update shows that the gateway‑based front door works..."
date: 2026-11-07T06:05:49+05:30
tags: [AWS, Bedrock, AIagents, Okta, Security]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Security", "Developer Tools"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-p2-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore adds EKS‑run agent with Okta‑driven governance

A second coding agent was added on Amazon Elastic Kubernetes Service (Amazon EKS) and wired through the same Amazon Bedrock AgentCore Gateway. The update shows that the gateway‑based front door works regardless of where an agent runs, while keeping the Okta‑driven delegation and Cedar policy enforcement intact.

## 🔍 Overview
- The original agent runs on **Amazon Bedrock AgentCore runtime** and is invoked for signed‑in users through **Okta Cross App Access (XAA)**.
- **Okta** decides which agent may act for a user and **Amazon Bedrock AgentCore Identity** redeems Okta’s grant inside the agent.
- The new addition is a **second agent (agent B)** deployed on **Amazon EKS**, using its own Okta identity but following the identical request flow.

## 🏗️ Architecture
- All agents reach a single **Gateway endpoint**; the Gateway holds the target registry and redeems the Okta grant.
- The topology consists of:
  - 1 agent (original) + 1 agent (EKS) 
  - 2 **Model Context Protocol (MCP) servers** acting as Gateway targets
  - Authorization checks embedded in each MCP server
- Request flow (illustrated for agent A):
  1. User signs in; the backend‑for‑frontend (BFF) exchanges the ID token for an **Identity Assertion JWT Authorization Grant (ID‑JAG)**.
  2. BFF invokes the agent on **AgentCore runtime** with the ID‑JAG.
  3. Agent forwards the ID‑JAG to the Gateway as the bearer token of its MCP session.
  4. Gateway inbound authorizer (issuer: Okta org auth server, audience: custom auth server, allowedClients pinned to the agent) accepts only that ID‑JAG.
  5. **Cedar policies** are evaluated for each tool listing and call before the Gateway invokes a target.
  6. For permitted calls, the Gateway uses **AgentCore Identity** to redeem the ID‑JAG for the target at Okta’s custom authorization server via the credential provider.
  7. Each hop emits OpenTelemetry spans collected by **AgentCore Observability** and visible in **Amazon CloudWatch Transaction Search**.
  8. Okta streams its System Log to CloudWatch through **Amazon EventBridge**.
- Agent B on EKS follows the identical path through its own Gateway instance.

| Component | Role |
|---|---|
| Amazon Bedrock AgentCore runtime | Executes each task in an isolated session inside the AWS account |
| Okta Cross App Access (XAA) | Determines which agent may act for a signed‑in user |
| AgentCore Identity | Redeems Okta’s grant inside the agent and at the Gateway |
| Gateway | Single front door; holds target registry, redeems grants, enforces Cedar policies |
| MCP servers | Act as Gateway targets; perform outbound token‑exchange via credential provider |
| Cedar policy set | Default‑deny policies evaluated at the Gateway before tools run |
| AgentCore Observability (CloudWatch) | Central view of all decisions and OpenTelemetry spans |
| BFF | Exchanges user ID token for ID‑JAG and starts the agent session |

## 🔐 Security & Governance
- Governance is proven by a deliberately small topology and a default‑deny **Cedar** policy set evaluated at the Gateway.
- The agent’s role holds **no token‑exchange or secret permissions**; all authorizations are performed by the Gateway.
- Policies bind each tool to the specific agent and the scope delegated by Okta.
- The inbound authorizer mirrors the runtime authorizer from the original deployment.
- Each MCP server has a static tool schema (listingMode = DEFAULT) so Cedar policies reference fixed tool names.

## 📈 Observability & Auditing
- **AgentCore Observability** (a capability of Amazon Bedrock AgentCore) streams every decision to **Amazon CloudWatch**.
- OpenTelemetry spans from each hop are indexed by **CloudWatch Transaction Search**.
- Okta’s System Log is forwarded to CloudWatch via **Amazon EventBridge**, providing a complete audit trail.

## 💰 Cost & Deployment
- Adding the second agent and the associated Gateway logic took **about 90 minutes**.
- **Amazon EKS control plane** costs **$0.10 per hour**, plus node and Auto‑Mode management fees; AgentCore features are billed based on usage.
- The solution builds on the AWS sample **08‑okta‑xaa‑delegation‑chain** on GitHub, with Part 2 additions layered on top.

## ✅ When to use
**Good fit**
- Scoped feature work, bug fixes, and tests on a trusted repository that declares its own setup and test commands.

**Not a fit**
- Untrusted code, because the agent runs the repository’s own commands without additional safety checks.
- Open‑ended work, because each task stops after three attempts.

The update demonstrates that Amazon Bedrock AgentCore can securely orchestrate remote coding agents from multiple runtimes, while preserving strict Okta‑driven access control, Cedar‑based tool gating, and end‑to‑end observability.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-p2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-p2-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/29/ML-21547-p2-3.png)

#AWS #Bedrock #AIagents #Okta #Security

---

*Source: [Govern AI agent access with Okta Cross App Access and Amazon Bedrock AgentCore – Part 2 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/govern-ai-agent-access-with-okta-cross-app-access-and-amazon-bedrock-agentcore-part-2/)*
*Source: [Extend Claude Code to remote sessions on Amazon Bedrock AgentCore with security controls | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/extend-claude-code-to-remote-sessions-on-amazon-bedrock-agentcore-with-security-controls/)*
