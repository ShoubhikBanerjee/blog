---
title: "Agentic Security adds verification gates and accuracy metrics to autonomous scanning"
slug: "agentic-security-adds-verification-gates-and-accuracy-metrics-to-autonomous-scanning"
description: "Clear Capabilities has updated its Agentic Security platform, an autonomous security assurance system, to emphasize deterministic evidence and a rigorous ten-stage lifecycle that prevents incomplete..."
date: 2026-11-16T22:14:27+05:30
tags: [AgenticSecurity, ClearCapabilities, SecurityAutomation, CodeScanning, AIEngineering]
categories: ["AI"]
image: "https://avatars.githubusercontent.com/u/280518569?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agentic Security adds verification gates and accuracy metrics to autonomous scanning

Clear Capabilities has updated its Agentic Security platform, an autonomous security assurance system, to emphasize deterministic evidence and a rigorous ten-stage lifecycle that prevents incomplete scans from being reported as clean.

## 🧩 How it works
Agentic Security pairs deterministic analysis with security agents that discover, challenge, and fix vulnerabilities. The platform distinguishes between model reasoning and mechanical evidence. A model proposes findings but never sets severity, confirms an exploit, or marks a fix as verified. 

- **Discovery and Challenge:** Agents look for weaknesses and then attempt to disprove their own findings through a skeptical falsification pass.
- **Verification:** Exploitability is proven where a reproducer exists, and patches are rescanned, linted, and tested before being written.
- **Knowledge Retention:** Novel confirmed weaknesses can become reusable rules so they are not rediscovered by a model each time.

The platform treats each finding as a claim to be tested rather than just a list item from a scanner. If a scan does not finish, or if an analyzer is unavailable or a verification step is skipped, the system does not report the code as safe.

## ⚙️ Key details
The system is built on six principles, each with dedicated documentation:

| Principle | Description |
| :--- | :--- |
| Evidence before severity | Severity, confidence, reachability, and exploit evidence are kept as separate facts. |
| Deterministic plus agentic | Agents are used where reasoning adds value, while mechanical evidence is used wherever possible. |
| Challenge your own findings | A falsification pass tries to disprove each finding to ensure confirmation is skeptical. |
| Prove, don't presume | Execution-backed proof is available where a reproducer exists. |
| Learn once | Confirmed discoveries are turned into reusable knowledge. |
| Never fake green | A scan that did not finish is never reported as clean. |

Capabilities are tracked with exactly one maturity level (GA, Preview, Labs, or Roadmap) in a central registry. A check fails the build if documentation contradicts this registry or presents a Roadmap item as shipped.

## 📉 Accuracy and Evidence
Independent accuracy has been measured once on code the engine was not built from. The results are low: localized precision is 6/19, recall is 6/278, and the F1 score is 0.040. These quality figures are published with the specific commands that produced them.

The tool treats the repository it scans as hostile, based on a documented agent threat model. To ensure a first run always finds something, the repository includes a small, deliberately vulnerable demo app.

## 🚀 Availability
Agentic Security is also described as an agentic security harness for Claude Code, Codex, Cursor, and Gemini CLI. It provides a `ci` entry point designed to be used in pipelines.

#AgenticSecurity #ClearCapabilities #SecurityAutomation #CodeScanning #AIEngineering

---

*Source: [Clear-Capabilities/agentic-security](https://github.com/Clear-Capabilities/agentic-security)*
