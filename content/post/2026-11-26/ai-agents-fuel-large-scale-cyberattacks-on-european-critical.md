---
title: "AI Agents Fuel Large-Scale Cyberattacks on European Critical Infrastructure"
slug: "ai-agents-fuel-large-scale-cyberattacks-on-european-critical-infrastructure"
description: "Recent alerts from Swiss and Italian cybersecurity agencies confirm that autonomous AI agents are conducting large‑scale attacks on critical‑infrastructure organisations, using publicly available..."
date: 2026-11-26T18:08:23+05:30
tags: [AIagents, Cybersecurity, CriticalInfrastructure, SwissNCSC, ItalianCSIRT]
categories: ["AI", "Cybersecurity", "AI Agents", "Critical Infrastructure", "Threat Intelligence"]
image: "https://www.bleepstatic.com/content/hl-images/2026/10/21/robot.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# AI Agents Fuel Large-Scale Cyberattacks on European Critical Infrastructure

Recent alerts from Swiss and Italian cybersecurity agencies confirm that autonomous AI agents are conducting large‑scale attacks on critical‑infrastructure organisations, using publicly available frameworks to find and exploit vulnerabilities quickly.

## 🔍 Overview
- Swiss NCSC: first reports of AI‑assisted attacks on Swiss organisations, including critical infrastructure across at least two sectors.
- "In recent days, the NCSC has received its first reports of cyberattacks against organisations in Switzerland in which the attack was carried out with the assistance of an AI agent," the Swiss NCSC said.
- Various organisations and operators of critical infrastructure across at least two sectors have been affected by these cyberattacks.
- In all cyberattacks known to the NCSC, the use of AI agents led to the successful compromise of the victim’s IT systems.
- Italian CSIRT Italia: detected large‑scale campaigns using autonomous AI agents on exposed endpoints; observed multiple agents working in parallel; rapid attacks exploiting weak passwords and known vulnerabilities; AI chained vulnerabilities, misconfigurations, compromised credentials.
- The agency described rapid attacks in which agents exploited weak passwords and known vulnerabilities in exposed endpoints, using frameworks to verify weaknesses and independently decide what to do next.
- In some cases, the agency observed multiple AI agents working in parallel to compromise a large number of systems within a few hours.
- In one instance involving a DeepSeek Harness setup, a coordinator assigned tasks to five AI agents that undertook a broad spectrum of operational stages, from information gathering to exploitation and persistence.
- Agents chained vulnerabilities, misconfigurations, and compromised credentials, leveraging exposed systems as a foothold to reach internal networks.

## 🧩 How it Works
"During the observed campaigns, autonomous agents demonstrated the ability to carry out complex, sustained activity to detect misconfigurations, link even low‑impact vulnerabilities into complex attack chains, and dynamically adapt their operating modules," CSIRT Italia says.

"They went as far as writing malicious code in real time to evade endpoint defenses and carry out actions deeper within the infrastructure."

## ⚙️ Key Details
| Framework | Involved in recent breaches and hacking incidents |
|---|---|
| ARTEX AI | Yes |
| CyberStrikeAI | Yes |
| DeepSeek Harness - Red Team | Yes |
| PentAGI | Yes |

- Reduce the number of systems exposed on the internet.
- Prioritize patching, especially internet‑facing systems within 24 hours of release.
- Add multi‑factor authentication (MFA) or passkey protection.
- Enforce least‑privilege principles.
- Disable remote management interfaces if not needed.
- Monitor control‑plane operations, authentication sources, traffic to internal networks, and outbound server traffic.
- The number of publicly available AI agents has nearly doubled since October, fueling large waves of attacks.

## 💡 Why it Matters
- AI agents can rapidly identify and exploit vulnerabilities across many systems.
- They chain low‑impact vulnerabilities into complex attack chains.
- They can write malicious code in real time to evade defenses.
- The attacks have already compromised IT systems in critical infrastructure.
- Urgent mitigation is required to protect exposed assets.


![figure](https://www.bleepstatic.com/c/w/w-claude-code-security.jpg)

![figure](https://www.bleepstatic.com/c/k/rmm-efficiency-challenge.jpg)

#AIagents #Cybersecurity #CriticalInfrastructure #SwissNCSC #ItalianCSIRT

---

*Source: [Italy and Switzerland warn of autonomous AI-driven cyberattacks](https://www.bleepingcomputer.com/news/security/italy-and-switzerland-warn-of-autonomous-ai-driven-cyberattacks/)*
