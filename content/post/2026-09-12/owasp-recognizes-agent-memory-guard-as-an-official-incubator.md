---
title: "OWASP Recognizes Agent Memory Guard as an Official Incubator Project"
slug: "owasp-recognizes-agent-memory-guard-as-an-official-incubator-project"
description: "The OWASP Foundation has officially recognized Agent Memory Guard as an Incubator Project, establishing it as an official project addressing memory and context poisoning (ASI06). Created and led by..."
date: 2026-09-12T22:02:50+05:30
tags: [OWASP, AgentMemoryGuard, AISecurity, OpenSource, LLM]
categories: ["AI", "AI Agents", "Cybersecurity", "Open Source"]
image: "https://avatars.githubusercontent.com/u/155815?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OWASP Recognizes Agent Memory Guard as an Official Incubator Project

The OWASP Foundation has officially recognized Agent Memory Guard as an Incubator Project, establishing it as an official project addressing memory and context poisoning (ASI06). Created and led by Vaishnavi Gudur with co-leader Anshul Rajkumar, the project provides a runtime defense designed to prevent AI agents from being weaponized through their own memory.

## 🔍 Overview

Modern AI agents persist memory across sessions, meaning anything written into that memory becomes a privileged input on the next turn. This introduces unique security vulnerabilities:

*   An attacker who plants text in the wrong field can override instructions, exfiltrate data, or hijack tool calls.
*   Because memory persists across sessions, the attack survives context resets.
*   While existing defenses run on user input at the front of the loop, memory poisoning runs directly on memory itself, presenting a completely different attack surface.

## 🧩 How it works

Agent Memory Guard addresses this vector by sitting directly between the agent and its memory store. It protects memory through the following mechanisms:

*   **Operation Screening:** It screens every operation through a pipeline of detectors and a declarative policy.
*   **Tampering Detection:** It uses SHA-256 baselines to flag out-of-band tampering with immutable keys.
*   **Runtime Defense:** It catches memory poisoning even after a context reset has occurred.

## ⚙️ Key details

The project offers a lightweight, local security implementation with the following specifications:

*   **Minimal Integration:** Requires only three lines of code to protect an agent's memory.
*   **No External Dependencies:** Requires no API keys and makes no external calls.
*   **Performance:** Runs locally at a median latency of 59 µs.
*   **Testing:** Tested against 55 real-world attack payloads across 4 threat categories.
*   **Industry Integration:** Named in the Memory Hardening mitigation as an open-source implementation of memory-hardening controls. The architecture was discussed with practitioners in issue threads on microsoft/autogen, langchain-ai/langgraph, BerriAI/litellm, and 567-labs/instructor.

## 🚀 Availability

Developers can try the live Memory Poisoning Lab to run a representative attack-and-block scenario directly in a web browser.

#OWASP #AgentMemoryGuard #AISecurity #OpenSource #LLM

---

*Source: [OWASP/www-project-agent-memory-guard](https://github.com/OWASP/www-project-agent-memory-guard)*
