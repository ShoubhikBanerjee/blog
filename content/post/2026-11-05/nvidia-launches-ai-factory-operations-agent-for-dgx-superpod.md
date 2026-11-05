---
title: "NVIDIA launches AI Factory Operations Agent for DGX SuperPOD automation"
slug: "nvidia-launches-ai-factory-operations-agent-for-dgx-superpod-automation"
description: "NVIDIA introduced the AI Factory Operations Agent to streamline internal DGX SuperPOD operations and reduce the manual effort required by NVIDIA SREs."
date: 2026-11-05T06:03:43+05:30
tags: [NVIDIA, AIAgents, Kubernetes, Observability]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Infrastructure Operations", "Kubernetes"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image2-3-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA launches AI Factory Operations Agent for DGX SuperPOD automation

NVIDIA introduced the AI Factory Operations Agent to streamline internal DGX SuperPOD operations and reduce the manual effort required by NVIDIA SREs.

## 🔍 Overview
- The agent suite runs on‑premises and is built on the NVIDIA NemoClaw blueprint.
- Sub‑agents communicate through the Model Context Protocol (MCP), which any organization can adopt.
- Interactions occur via a natural‑language chat interface that surfaces recommendations and audit trails.

## 🧩 How it works
- A user‑facing runtime receives SRE queries from the chat UI and routes them to the appropriate domain agent via NemoClaw.
- Agents connect to infrastructure through OpenClaw plugins and MCP servers; each MCP exposes a focused set of approved operational tools.
- Inference uses locally served NVIDIA Nemotron open models.
- The framework runs on internal NVIDIA DGX H100, DGX B200, and DGX GB300 production clusters.
- Shell execution creates a per‑session Kubernetes sandbox instead of running commands in the main gateway pod.
- Kubernetes inspection uses a server‑side `run_kubectl` tool with a pinned kubectl binary and read‑only credentials; OpenShell never receives Kubernetes credentials.

## 🤖 Agents & Capabilities
| Agent | Purpose |
|-------|---------|
| Job Recovery Agent | Detects training job failures and goodput degradation; performs multi‑layer root‑cause analysis across scheduler, application, hardware, and network layers; recommends recovery steps when root cause is confirmed |
| Hardware Agent | Triages hardware faults at the device level—PCIe errors, ECC errors, GPU issues, NVMe failures, and thermal anomalies—tracing symptoms down to the specific component |
| Observability Agent | Queries historical Prometheus, telemetry, and integrated Grafana Loki logs to create dashboards dynamically and display them directly in the web UI |
| Research Agent | Searches preloaded documentation including NVIDIA Mission Control manuals and DGX SuperPOD reference architectures and deployment guides |
| Kubernetes Agent | Provides read‑only operational awareness across pods, services, deployments, GPU resources, node status, and scheduling state |
| Cluster Management Agent | Interfaces with NVIDIA Base Command Manager APIs through diagnostic MCP tools for advisory cluster management and troubleshooting |

## ⚙️ Deployment Details
- The agent runs as a Kubernetes control‑plane application.
- Helm deploys the UI, OpenClaw gateway, MCP tool servers, inference endpoint, and NVIDIA OpenShell runtime as separate Kubernetes services.
- The chat UI sends each request to NemoClaw, which routes it to the appropriate domain agent.
- The runtime receives the AI Factory Operations Agent workspace, selected skills, and command policy; its lifecycle does not modify existing services or production workloads.
- Kubernetes service accounts and RBAC define the cluster resources each tool can inspect.

## 🚀 Why it matters
- Automates detection of failures and root‑cause correlation across multiple layers.
- Provides clear, actionable recommendations through a conversational interface.
- Maintains auditability of every SRE action.
- Supports on‑premises deployment, data sovereignty, and extensibility by allowing custom MCP servers and APIs.
- NVIDIA tracks RCA accuracy and SRE agreement to continuously improve the framework and expand the agent ecosystem.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/nemoclaw-featured-660x370-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/OpenShellKVcroppped-660x370-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/03/graphic-ai-factory-660x370.png)

#NVIDIA #AIAgents #Kubernetes #Observability

---

*Source: [How NVIDIA Uses AI Agents to Streamline AI Factory Operations | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-nvidia-uses-ai-agents-to-streamline-ai-factory-operations/)*
