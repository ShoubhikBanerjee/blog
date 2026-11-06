---
title: "Open‑Source AI Security Operations Center (AiSOC) Enables Self‑Hosted Threat Detection"
slug: "opensource-ai-security-operations-center-aisoc-enables-selfhosted-threat-detection"
description: "An open‑source AI Security Operations Center called **AiSOC** has been released. It runs on‑premises, requires no external API keys, and provides end‑to‑end alert fusion, automated triage, and..."
date: 2026-11-06T22:02:31+05:30
tags: [AISEC, OpenSource, Cybersecurity, LLM]
categories: ["AI", "Cybersecurity", "Artificial Intelligence", "Open Source Software", "Security Operations"]
image: "https://avatars.githubusercontent.com/u/19245630?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Open‑Source AI Security Operations Center (AiSOC) Enables Self‑Hosted Threat Detection

An open‑source AI Security Operations Center called **AiSOC** has been released. It runs on‑premises, requires no external API keys, and provides end‑to‑end alert fusion, automated triage, and auditable AI‑driven investigation.

## 🔍 Overview
- Self‑hostable AI SOC licensed under MIT.
- Ingests security telemetry from existing tools.
- Detects, correlates, and investigates threats with LLM agents.
- Every agent step is recorded in a replayable decision ledger.

## 🧩 How it works
- Telemetry arrives from your security tools and is normalized by AiSOC.
- The platform runs **2,966 executable rules** from a **7,407‑rule library** to fire alerts.
- Fired alerts are grouped into incidents and handed to an AI agent.
- The agent’s prompts, tool calls, and reasoning are fully auditable.
- After investigation the agent proposes a response that a human must approve.
- New threat‑intelligence data (e.g., the CISA KEV catalog) re‑sweeps historical data, again requiring human approval before any vendor interaction.

## ⚙️ Key details
- Alert fusion, LLM‑agent triage, MITRE ATT&CK investigation.
- Replayable decision ledger for every agent step.
- MCP server ships for Claude, Cursor, and Continue.
- No API keys required; the real CISA KEV catalog is loaded minutes after boot.
- Alerts show the originating connector; automated triage displays the local model’s verdict, confidence, and rationale verbatim.

## 🚀 Availability & Installation
| Method | Command |
|--------|---------|
| Windows PowerShell | `iwr -useb https://raw.githubusercontent.com/beenuar/AiSOC/main/install.ps1 | iex` |
| Linux/macOS curl | `curl -fsSL https://raw.githubusercontent.com/beenuar/AiSOC/main/install.sh | bash` |
| Offline demo (no Docker) | `pip install aisoc-sandbox && aisoc-sandbox demo` |

- Docker‑Compose v2 is optional; requires 8 GB memory, 20 GB free disk, Python 3.9+, and Bash.
- `make doctor` validates the environment; `make up` creates `.env` with fifteen generated secrets and prints a one‑time admin password.
- `make clean` removes the ~2 GB model volume; `make bootstrap ARGS=--reset-password` regenerates a lost admin password.
- Ports already in use are detected, reported, and the install proceeds, publishing a new free port and moving the console address.
- `make smoke` posts a real event through Kafka, detection, correlation, and Postgres to demonstrate end‑to‑end operation.

## 💡 Why it matters
- Provides a fully auditable AI decision path, addressing trust concerns in automated security workflows.
- Eliminates dependence on external API keys, enhancing privacy and reducing cost.
- Offers a turnkey, self‑hosted solution that can run on a single server or via GitHub Codespaces.
- Enables rapid threat‑intelligence updates and re‑analysis of historic data without vendor involvement.

#AISEC #OpenSource #Cybersecurity #LLM

---

*Source: [beenuar/AiSOC](https://github.com/beenuar/AiSOC)*
