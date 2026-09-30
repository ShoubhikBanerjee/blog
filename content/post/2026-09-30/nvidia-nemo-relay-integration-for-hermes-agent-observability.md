---
title: "NVIDIA NeMo Relay Integration for Hermes Agent Observability"
slug: "nvidia-nemo-relay-integration-for-hermes-agent-observability"
description: "The Hermes Agent harness now includes native integration with NVIDIA NeMo Relay, allowing developers to record and evaluate agent sessions, turns, model calls, and tool calls."
date: 2026-09-30T22:03:54+05:30
tags: [NVIDIA, NeMoRelay, HermesAgent, OpenTelemetry, AIAgents]
categories: ["AI", "AI Agents", "Software Development", "Observability"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/Tracing-Agent-Harness-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA NeMo Relay Integration for Hermes Agent Observability

The Hermes Agent harness now includes native integration with NVIDIA NeMo Relay, allowing developers to record and evaluate agent sessions, turns, model calls, and tool calls.

## 🧩 How it works
NeMo Relay records lifecycle events as work begins and ends, preserving timing and parent-child relationships. This integration utilizes several formats and standards for observability:

| Format/Standard | Description |
| :--- | :--- |
| Agent Trajectory Observability Format (ATOF) | A JSONL log of scope starts, ends, and point-in-time marks with IDs and timestamps to reconstruct the agent run. |
| Agent Trajectory Interchange Format (ATIF) | A step-by-step JSON record of agent interactions, tool calls, and observations assembled from lifecycle events. |
| OpenTelemetry with OpenInference | Records the run as parent-child spans, using OpenInference to label agent, LLM, and tool spans and define their attributes. |

## ⚙️ Key details
Users can run Hermes Agent examples using a self-contained environment (Python 3.11, Hermes 0.21.1, and NeMo Relay 0.8.3) created via a setup script in the `nemoclaw-community` repository. 

Capabilities and constraints include:
* **Terminal Tool Sandbox**: Hermes uses a terminal tool to run Python scripts inside an isolated Docker container that cannot access the network, repository checkout, or NVIDIA API key.
* **Host Security**: Hermes cannot fall back to running terminal commands on the host.
* **Observability Tools**: Users can explore OpenTelemetry traces in Arize Phoenix.
* **Evaluation**: The Hermes ToolPerf case study demonstrates using this approach to evaluate harness changes across repeated runs by combining task verification with trace evidence.

## 🚀 Availability
To get started, the following prerequisites are required:
* macOS or Linux
* Git and curl
* Docker Desktop or Docker Engine
* An NVIDIA Build API key for NVIDIA Nemotron 3.5 Lightning

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/Tracing-Agent-Harness-1024x576-png.webp)

#NVIDIA #NeMoRelay #HermesAgent #OpenTelemetry #AIAgents

---

*Source: [Tracing Agent Harness Behavior with NVIDIA NeMo Relay | NVIDIA Technical Blog](https://developer.nvidia.com/blog/tracing-agent-harness-behavior-with-nvidia-nemo-relay/)*
