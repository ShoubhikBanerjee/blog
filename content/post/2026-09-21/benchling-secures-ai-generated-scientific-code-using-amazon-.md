---
title: "Benchling Secures AI-Generated Scientific Code Using Amazon Bedrock AgentCore"
slug: "benchling-secures-ai-generated-scientific-code-using-amazon-bedrock-agentcore"
description: "Benchling has implemented AgentCore Code Interpreter, a capability of Amazon Bedrock AgentCore, to securely execute AI-generated scientific code for researchers across thousands of tenants."
date: 2026-09-21T22:03:11+05:30
tags: [AmazonBedrock, AIagents, Cybersecurity, CloudComputing, AWS]
categories: ["AI", "AI Agents", "Cloud Security", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/26/ML-21025-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Benchling Secures AI-Generated Scientific Code Using Amazon Bedrock AgentCore

Benchling has implemented AgentCore Code Interpreter, a capability of Amazon Bedrock AgentCore, to securely execute AI-generated scientific code for researchers across thousands of tenants.

## 🔍 Overview

Amazon Bedrock AgentCore is a platform designed to build, connect, and optimize agents at scale using any framework or model. Benchling utilizes this platform in Amazon Virtual Private Cloud (VPC) mode to handle several primary use cases:

* AI agent-generated scientific code
* Simple calculations
* Code-generation sandboxes

## 🧩 How it works

To prevent data exfiltration and ensure tenant isolation, Benchling employs an architecture that separates production environments from code execution:

* **Production Account**: Contains the Benchling Stack, IAM Roles, AWS STS, and customer data in Amazon S3.
* **Untrusted Code Account**: A separate AWS account hosting the ACCI VPC and a container-based execution environment using gVisor for kernel-level isolation.

Tasks are dispatched from the production account to the untrusted account. Because the solution cannot use one IAM role per tenant to avoid unsustainable role sprawl, per-job credentials are injected into each session via AWS Security Token Service (AWS STS) to scope data access dynamically.

## ⚙️ Key details

Security is enforced through multiple layers of network and access controls:

| Control Mechanism | Function |
| :--- | :--- |
| **VPC Configuration** | No internet gateway and no NAT gateway; restricts outbound paths to the public internet. |
| **Security Group** | Restricts the Code Interpreter to port 443. |
| **Route 53 Resolver DNS Firewall** | Applies a three-priority policy: blocks malicious domains (Priority 10), allows explicitly listed endpoints (Priority 100), and blocks all others (Priority 200). |
| **VPC Endpoints** | Provides the only permitted network paths via S3 Gateway and Interface endpoints.
| **Network Controls** | Block HTTP, restrict egress ports, and limit outbound connections. |

## 💡 Why it matters

This architecture ensures that each session accesses only that specific tenant's data with no cross-tenant visibility. A Continuous Validation suite runs integration tests to simulate exfiltration attempts against the configuration. Currently, this architecture processes more than 600 code execution sessions per day across more than 250 tenants per week with zero security incidents.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/Benchling-agentcore-ci-revised.drawio.png)

#AmazonBedrock #AIagents #Cybersecurity #CloudComputing #AWS

---

*Source: [How Benchling secured multi-tenant AI agents with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-benchling-secured-multi-tenant-ai-agents-with-amazon-bedrock-agentcore/)*
