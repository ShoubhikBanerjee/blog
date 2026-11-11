---
title: "Microsoft discovers “Lazarus” backdoor that reprograms dormant neurons in AI agents"
slug: "microsoft-discovers-lazarus-backdoor-that-reprograms-dormant-neurons-in-ai-agents"
description: "Microsoft researchers have identified a new backdoor technique, dubbed “Lazarus,” that can silently reprogram a handful of dormant neurons in a large language model, enabling an otherwise normal AI..."
date: 2026-11-11T06:08:28+05:30
tags: [AIsecurity, ModelProvenance, Backdoor, MicrosoftFoundry]
categories: ["AI", "Machine Learning", "AI Security", "AI Agents", "Software Engineering"]
image: "https://www.microsoft.com/en-us/research/wp-content/uploads/2026/11/MSR-BLG_LAZ_HERO.png"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft discovers “Lazarus” backdoor that reprograms dormant neurons in AI agents

Microsoft researchers have identified a new backdoor technique, dubbed “Lazarus,” that can silently reprogram a handful of dormant neurons in a large language model, enabling an otherwise normal AI agent to execute malicious commands when a hidden trigger fires.

## 🔍 Overview
- “Lazarus” can reprogram fewer than 10 dormant neurons in an LLM without any additional training.
- The altered model passes standard safety evaluations and behaves normally until a trigger appears.
- A trigger can be as simple as a date change (e.g., the clock passing midnight into 2027) that causes the agent to download and run attacker code.
- The technique is especially serious for AI agents that have tool or terminal access.

## 🧩 How it works
- The backdoor edits the model’s weight matrix directly, targeting dormant neurons that rarely affect ordinary outputs.
- Because the change is tiny, it does not affect benchmark performance, allowing the model to clear typical safety tests.
- When the hidden trigger is observed, the agent executes the malicious payload with whatever permissions the user has granted it.

## ⚠️ Risks
- Silent download and execution of attacker‑supplied code.
- Theft of secrets accessible to the agent.
- Execution of destructive commands while still appearing safe in evaluations.
- Large attack surface inherent to AI agents that can invoke external tools.

## 🛡️ Defenses
- **Microsoft Foundry** verifies model provenance, ties each model to a trusted publisher, and scans the surrounding software environment before onboarding open‑weight models.
- Models are run inside Microsoft‑controlled containers that are separately scanned for critical vulnerabilities.
- Ongoing development of:
  - AI‑powered weight scanning.
  - Red‑team tools for detecting anomalous model modifications.
  - Cryptographic model signing with tamper‑evident provenance and audit trails.
- Frontier agents can be asked to spot anomalous weight modifications, providing an additional detection signal.

| Defense Mechanism | Description |
|-------------------|-------------|
| Weight Scanning   | Uses AI to analyze model weights for unexpected changes. |
| Red‑Team Harness  | Internal tools that probe models for hidden backdoors. |
| Cryptographic Signing | Adds verifiable provenance and tamper‑proof audit trails to model files. |

## 🚦 Detection limits
- No scan can prove beyond any doubt that a model is safe.
- Reliable detection requires diff‑ing against the original, unmodified weights, making provenance critical.
- Even with strong provenance, risk remains if a trusted provider is compromised (e.g., through its training infrastructure or an insider).

## 📅 Outlook
- Microsoft is turning detection techniques into a red‑team harness and exploring weight‑scanning signals for open‑weight model onboarding.
- Plans are underway to require cryptographic signing of models with verifiable provenance.
- The research began as a quick experiment in March, where Claude Code with Opus 4.5 was asked to hard‑wire a few activations without training—and succeeded.
- Ongoing collaboration between researchers and security teams aims to translate these findings into product defenses and guidance that keep customers protected.

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/11/Fig1_Laz.png)

![figure](https://uhf.microsoft.com/images/microsoft/RE1Mu3b.png)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2024/09/Screenshot-2024-09-17-at-2.50.08 PM.jpg)

#AIsecurity #ModelProvenance #Backdoor #MicrosoftFoundry

---

*Source: [Lazare, veni foras: Reprogramming Dormant Neurons to Backdoor AI Agents - Microsoft Research](https://www.microsoft.com/en-us/research/blog/lazare-veni-foras-reprogramming-dormant-neurons-to-backdoor-ai-agents/)*
