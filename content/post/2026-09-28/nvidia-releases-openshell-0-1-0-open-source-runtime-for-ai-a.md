---
title: "NVIDIA Releases OpenShell 0.1.0 Open-Source Runtime for AI Agent Governance"
slug: "nvidia-releases-openshell-0-1-0-open-source-runtime-for-ai-agent-governance"
description: "NVIDIA has introduced OpenShell 0.1.0, an open-source runtime designed to define and enforce the systems and data that AI agents can access. OpenShell serves as the runtime layer of the broader..."
date: 2026-09-28T18:02:46+05:30
tags: [NVIDIA, OpenShell, AIAgents, OpenSource, Cybersecurity]
categories: ["AI", "AI Agents", "Cybersecurity", "Enterprise Software"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/OpenShell-Controls-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases OpenShell 0.1.0 Open-Source Runtime for AI Agent Governance

NVIDIA has introduced OpenShell 0.1.0, an open-source runtime designed to define and enforce the systems and data that AI agents can access. OpenShell serves as the runtime layer of the broader NVIDIA Open Agent Safety Platform, which provides protection across application, runtime, and infrastructure layers.

## 🔍 Overview

OpenShell enables teams to grant agents specific capabilities required for tasks while enforcing permissions outside of the workload. It supports several frameworks, including:
- Codex
- Claude Code
- Pi
- Hermes

## 🧩 How it works

OpenShell utilizes a three-component architecture to manage agent security:

| Component | Function |
| :--- | :--- |
| OpenShell Gateway | Manages the lifecycles and policies of many sandboxes. |
| OpenShell Supervisor | Paired with each sandbox; runs outside the workload to check outbound requests against policy. |
| OpenShell Sandbox | Runs the workload using kernel-level controls over processes and filesystem, with no network path except through the supervisor. |

Policies are authored in YAML and compiled to OPA/Rego for evaluation during outbound requests. The supervisor can inspect Model Context Protocol (MCP), GraphQL, and HTTP traffic, which allows it to block a write request while permitting a data query through the same API. All policy decisions are recorded in an Open Cybersecurity Schema Framework (OCSF) audit trail.

## ⚙️ Key details

OpenShell 0.1.0 provides several technical capabilities:
- **Credential Management:** Real credentials remain outside the agent workload and are bound to authorized requests.
- **Flexible Compute:** Support for experiments and data processing on GPUs or CPUs across Kubernetes environments, VMs, and containers.
- **Governance Integration:** Ability to connect custom checks, governance systems, and third-party security services to enforcement outside the workload.
- **Multi-tenancy:** Support for multiple customers or teams using separate permissions, workspaces, and service access on shared infrastructure.
- **Policy Verification:** Tools for human and AI reviewers to identify where requested permissions exceed defined security boundaries.

## 🚀 Availability

OpenShell is open source and available for enterprise adoption. Organizations are currently adopting the runtime for various applications:
- **Cadence:** Using OpenShell for chip design with its ChipStack Autonomous RTL Design Engineer.
- **Slack:** Building an on-demand agent platform for task automation.
- **Gecko Robotics:** Governing agents that make decisions on physical robots.
- **Other sectors:** Accelerated computing and enterprise automation.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/OpenShell-Controls-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/figure-1-2.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/figure-2-2.webp)

#NVIDIA #OpenShell #AIAgents #OpenSource #Cybersecurity

---

*Source: [Add Runtime Controls to AI Agents with NVIDIA OpenShell | NVIDIA Technical Blog](https://developer.nvidia.com/blog/add-runtime-controls-to-ai-agents-with-nvidia-openshell/)*
