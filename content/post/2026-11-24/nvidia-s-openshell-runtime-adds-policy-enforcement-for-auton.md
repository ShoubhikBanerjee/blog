---
title: "NVIDIA's OpenShell runtime adds policy enforcement for autonomous AI agents"
slug: "nvidia-s-openshell-runtime-adds-policy-enforcement-for-autonomous-ai-agents"
description: "NVIDIA has contributed OpenShell, an open source runtime for autonomous AI agents, to the Cloud Native Computing Foundation (CNCF), where it is now a Sandbox project. The Apache 2.0 licensed tool..."
date: 2026-11-24T22:08:41+05:30
tags: [NVIDIA, OpenShell, AIAgents, Security, CNCF]
categories: ["AI", "AI Agents", "Security", "Cloud Native", "Runtime"]
image: "https://res.cloudinary.com/snyk/image/upload/v1689708917/blog-feature-ai-blue.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA's OpenShell runtime adds policy enforcement for autonomous AI agents

NVIDIA has contributed OpenShell, an open source runtime for autonomous AI agents, to the Cloud Native Computing Foundation (CNCF), where it is now a Sandbox project. The Apache 2.0 licensed tool focuses on enforcing security policies across agent interactions, ensuring that agents only access resources explicitly permitted by predefined rules.

## 🔍 Overview
OpenShell acts as a runtime layer that monitors and restricts the behavior of autonomous AI agents. It enforces declared policies on every file access, system call, and network connection. A key feature of the runtime is its ability to verify which specific binary initiates a network connection, preventing agents from exploiting trusted applications to send data to unauthorized destinations.

## 🧩 How it works
The enforcement mechanism operates at multiple levels of the stack:
* **Network Policy:** Rules can specify that only certain binaries may reach specific endpoints. For example, a policy can restrict the Snyk binary to only access `api.snyk.io`, preventing the agent from using Snyk's access to exfiltrate data elsewhere.
* **Credential Handling:** OpenShell holds API keys and injects them only into requests bound for approved endpoints. In a test build involving Claude Code, Anthropic keys never entered the sandbox environment.
* **Default Denial:** New sandboxes start with no network access. When an agent attempts to reach a new host, OpenShell blocks the request and generates a draft rule for human approval.
* **MCP Server Governance:** Enforcement runs through the agent's hooks at tool-call time. This covers local Model Context Protocol (MCP) servers that do not touch the network. If an agent calls a tool on an unapproved server, the governance system stops the call and identifies the responsible policy.

## ⚙️ Key details
A reference build combines OpenShell with specific security controls to demonstrate the architecture:

| Component | Function |
| :--- | :--- |
| Base Image | NVIDIA's own Ubuntu base image |
| Integrated Tools | Claude Code and four Snyk controls |
| Startup Scanning | Agent supply chain security scans the sandbox, flagging potential prompt injection and insecure credential handling with specific line numbers |
| Code Security | Snyk Studio's "Secure at Inception" hook scans agent output, flagging issues like SQL injection and holding the turn until fixes are applied |
| Inventory | Each sandbox appears in Evo as a distinct machine alongside developer laptops and Docker Sandboxes |

The architecture relies on binaries being fixed at build time and checksum-verified. Because OpenShell only permits program execution from system folders such as `/usr`, tools like Snyk are built directly into the image rather than installed at runtime.

## 🚀 Availability
OpenShell is available as an open source project under the Apache 2.0 license. The tested version was OpenShell 0.1.6. A single `run.sh` command can build the reference image, store credentials in OpenShell, and start the sandbox with a pre-approved network policy.

#NVIDIA #OpenShell #AIAgents #Security #CNCF

---

*Source: [How to Secure AI Coding Agents in NVIDIA OpenShell with Evo | Snyk](https://snyk.io/blog/secure-ai-coding-agents-nvidia-openshell/)*
