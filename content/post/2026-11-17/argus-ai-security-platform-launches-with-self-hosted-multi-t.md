---
title: "Argus AI Security Platform Launches with Self-Hosted Multi-Tenant Capabilities"
slug: "argus-ai-security-platform-launches-with-self-hosted-multi-tenant-capabilities"
description: "A new self-hosted, multi-tenant, and MIT-licensed security platform named Argus has been released to watch cloud, identity, code, endpoints, network, and Kubernetes environments."
date: 2026-11-17T18:10:30+05:30
tags: [AISecurity, AIAgents, Cybersecurity, DevSecOps, CloudSecurity]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Cybersecurity", "Software Development"]
image: "https://avatars.githubusercontent.com/u/53983704?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Argus AI Security Platform Launches with Self-Hosted Multi-Tenant Capabilities

A new self-hosted, multi-tenant, and MIT-licensed security platform named Argus has been released to watch cloud, identity, code, endpoints, network, and Kubernetes environments.

## 🔍 Overview
Argus catches attacks at machine speed, investigates them with AI agents, and contains them in seconds. The platform operates offline for air-gapped installs and ensures security data never leaves the user's hands.

## 🧩 How it works
- Nine specialist agents triage, investigate, and hunt using read-only tools.
- Agents can propose a fix but never execute one; their one write-capable tool creates a pending request.
- Everything agents read is treated as untrusted data so prompt injections become signals instead of hijacks.
- Autonomous response playbooks act the moment a detection fires using a catalog of 27 typed actions.
- Every autonomous feature ships off by default so users can enable autonomy gradually.

## ⚙️ Key details
- **AI Gateway**: Puts OpenAI and Anthropic traffic behind org-held keys, model allowlists, data-loss prevention, prompt-injection flags, and budgets.
- **Shadow-AI Discovery**: Finds services used without approval via network, cloud, and SSO telemetry.
- **Canaries**: Built for agents with hidden prompt injections, agent rules files, a fake MCP server, and fake LLM API keys.
- **Attack Simulator**: Replays eight AI-driven attack scenarios in an isolated sandbox tenant.
- **Pentesting**: Autopilot and native autonomous pentesting plan tests and run them through a scope-checked harness.
- **Vulnerability Enrichment**: CVE findings are enriched with CISA's Known Exploited Vulnerabilities list and EPSS scores, automatically raising severity.

## 🚀 Availability
- Deployment options include Docker Compose for pilots, Helm for Kubernetes, and Terraform for AWS and Azure.
- Encrypted backups run on a schedule and land on disk, S3, or Azure with single-command restore and verification checks.
- Control mappings for SOC 2, NIST 800-171, and ISO 27001 are included.

#AISecurity #AIAgents #Cybersecurity #DevSecOps #CloudSecurity

---

*Source: [thomasunise/argus](https://github.com/thomasunise/argus)*
