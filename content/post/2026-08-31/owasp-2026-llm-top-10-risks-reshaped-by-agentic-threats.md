---
title: "OWASP 2026 LLM Top 10 risks reshaped by agentic threats"
description: "Every AI security framework names the risks you have to control. Zenity is built to implement those controls at runtime."
date: 2026-08-31T22:56:10+05:30
tags: [OWASP2026, LLMSecurity, AIAgents, PromptInjection, RuntimeControls]
categories: [AI]
image: "https://cdn.sanity.io/images/bqvkdjz2/production/0be8f03a2d2a895a3aea51d71f51056a045b4793-1921x1080.png?w=1920&q=85&auto=format"
author: "Shoubhik Banerjee"
draft: false
---

# OWASP 2026 LLM Top 10 risks reshaped by agentic threats

Every AI security framework names the risks you have to control. Zenity is built to implement those controls at runtime.

## 🔍 Overview

The 2026 OWASP Top 10 for LLM Applications is the current list of the most critical security risks in applications built on large language models, published by the OWASP GenAI Security Project. It leads with Prompt Injection (LLM01), Sensitive Information Disclosure (LLM02), and Excessive Agency (LLM03), and it covers the model as a component inside an application. When the model becomes an actor with tools and memory, you pair it with the OWASP Top 10 for Agentic Applications 2026, which picks up at ASI01.

The 2026 list re-ranks the 2025 list, but doesn't change the cast of risks. All ten classes carried over; however, the order shifted toward agents, and one entry got a new name. Prompt Injection and Sensitive Information Disclosure held their ground at first and second. The headline move is Excessive Agency, which jumped from sixth in 2025 to third in 2026, which is where the incident data behind the revision pointed. Unbounded Consumption climbed from tenth to sixth, and Misinformation moved from ninth to seventh. Improper Output Handling fell the other way, from fifth all the way to tenth. Supply Chain, Data and Model Poisoning, Hidden Context Exposure, and Vector and Embedding Weaknesses each slid down one slot. The one rename is System Prompt Leakage, now Hidden Context Exposure (LLM08), broadened to cover hidden context and not just the system prompt.

If you built controls against the 2025 numbering, the class names still hold, but re-read LLM01. Its scope widened in 2026 to cover cross-modal injection, memory persistence, and agentic blast radius.

## 🧩 How it works

Zenity maps to this list, where a runtime control can actually change the outcome. Paste a booby-trapped instruction into a chat window, and nothing much happens. The model reads the poisoned text, maybe repeats something dumb or coughs up a snippet it shouldn't, and you close the tab. Give that same model a tool, a token, and a mailbox, and the same instruction turns into an exfiltration run at your privilege level. Nothing about the model changed. What changed is that it can act.

That is the whole story of the 2026 OWASP Top 10 for LLM Applications, and Zenity is the platform built to close it. Zenity watches what the model does at runtime and blocks the action before it happens.

Zenity covers this list from two directions:
- AISPM surfaces weak configurations before anything runs.
- AIDR detects threats at runtime, and Inline Prevention, its real-time enforcement path, blocks the offending action on the platforms where it's supported. Prevented actions land in the same AIDR findings view.

AIDR's engine is hybrid: deterministic rules mapped to OWASP LLM and MITRE ATLAS, plus LLM-based intent-aware detections that run asynchronously. The framework tags are wired into detection.

## ⚙️ Key details

| OWASP 2026 Entry | Old Rank | New Rank | Key Change |
|------------------|----------|----------|------------|
| Prompt Injection (LLM01) | 1 | 1 | Scope widened to cover cross-modal injection, memory persistence, and agentic blast radius |
| Sensitive Information Disclosure (LLM02) | 2 | 2 | No change |
| Excessive Agency (LLM03) | 6 | 3 | Moved up due to incident data |
| Unbounded Consumption (LLM04) | 10 | 6 | Moved up |
| Misinformation (LLM05) | 9 | 7 | Moved up |
| Improper Output Handling (LLM06) | 5 | 10 | Moved down |
| Supply Chain (LLM07) | 4 | 5 | Moved down |
| Hidden Context Exposure (LLM08) | — | 8 | Renamed from System Prompt Leakage, broadened scope |
| Data and Model Poisoning (LLM09) | 3 | 4 | Moved down |
| Vector and Embedding Weaknesses (LLM10) | 7 | 9 | Moved down |

Prevent applies on platforms where Zenity runs inline, meaning Copilot Studio, Microsoft Foundry, and coding agents through hooks. On poll-only platforms such as M365 Copilot, Agentforce, Vertex AI, Gemini Enterprise, and ServiceNow, coverage is detection and posture only.

## 💡 Why it matters

The 2026 OWASP Top 10 for LLM Applications is vendor-neutral. It does not mean OWASP endorses Zenity or any other vendor. The list is vendor-neutral. The mapping below is Zenity's own. The shift toward agentic threats highlights a critical gap: models that act on instructions can turn benign prompts into real breaches. Zenity's runtime controls address this gap by blocking harmful actions before they occur, closing the loop between risk identification and enforcement.

#OWASP2026 #LLMSecurity #AIAgents #PromptInjection #RuntimeControls

---

*Source: [Zenity's Coverage of the 2026 OWASP Top 10 for LLM Apps](https://zenity.io/blog/how-zenity-implements-the-owasp-top-10-for-llm-applications)*
