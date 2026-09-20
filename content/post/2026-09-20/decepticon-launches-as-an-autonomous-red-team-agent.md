---
title: "Decepticon Launches as an Autonomous Red Team Agent"
slug: "decepticon-launches-as-an-autonomous-red-team-agent"
description: "Decepticon is a new autonomous red team agent now available in the cloud to assist with autonomous red-team engagements directly from the browser."
date: 2026-09-20T18:01:49+05:30
tags: [Decepticon, AIAgents, Cybersecurity, Pentesting]
categories: ["AI", "AI Agents", "Cybersecurity", "Software Development"]
image: "https://avatars.githubusercontent.com/u/211282590?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Decepticon Launches as an Autonomous Red Team Agent

Decepticon is a new autonomous red team agent now available in the cloud to assist with autonomous red-team engagements directly from the browser.

## 🔍 Overview
Decepticon functions as both a platform and a client SDK for building agents, research integrations, and custom orchestrators. It aims to serve as an offensive vaccine for the AI-driven threat landscape.

## 🧩 How it works
The agent platform utilizes a core management plane that includes LiteLLM, PostgreSQL, Neo4j, Skillogy, LangGraph, and a sandbox. Users can initiate specialist workloads on demand, such as BloodHound CE, Sliver C2, or Ghidra MCP.

| Component | Description |
| :--- | :--- |
| Core Management Plane | Includes LiteLLM, PostgreSQL, Neo4j, Skillogy, LangGraph, and sandbox |
| Specialist Workloads | Includes BloodHound CE, Sliver C2, and Ghidra MCP |
| Client SDK | Ships agent factories, middleware, tools, and skills |

## ⚙️ Key details
Decepticon is supported on macOS, Linux, and Windows. It provides a CLI for interaction, including an onboarding wizard for API keys and model profiles.

- The SDK can be installed via PyPI: `pip install decepticon`.
- It offers specialized packages such as `pip install "decepticon[neo4j]"` for knowledge-graph attack-chain tools.
- Running agents requires services like LLM proxies and sandbox environments, which can be managed via the provided Docker stack.

## 🚀 Performance
In XBOW validation benchmarks, Decepticon achieved a 98.08% pass rate across 104 challenges.

| Level | Pass Rate |
| :--- | :--- |
| Easy (Level 1) | 45 / 45 (100%) |
| Medium (Level 2) | 50 / 51 (98.0%) |
| Hard (Level 3) | 7 / 8 (87.5%) |
| Total | 102 / 104 (98.08%) |

#Decepticon #AIAgents #Cybersecurity #Pentesting

---

*Source: [BitterSecurity/Decepticon](https://github.com/BitterSecurity/Decepticon)*
