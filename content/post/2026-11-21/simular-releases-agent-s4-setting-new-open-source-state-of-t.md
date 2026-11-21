---
title: "Simular Releases Agent S4, Setting New Open-Source State of the Art on OSWorld"
slug: "simular-releases-agent-s4-setting-new-open-source-state-of-the-art-on-osworld"
description: "Simular has released Agent S4, an autonomous computer-use scientist that evolves the interfaces its agents work through from task experience. Alongside the release, Simular published the paper..."
date: 2026-11-21T12:13:14+05:30
tags: [Simular, AgentS4, ComputerUse, OSWorld, OpenSource]
categories: ["AI", "AI Agents", "Machine Learning", "Computer Vision", "Benchmarks"]
image: "https://avatars.githubusercontent.com/u/80465946?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Simular Releases Agent S4, Setting New Open-Source State of the Art on OSWorld

Simular has released Agent S4, an autonomous computer-use scientist that evolves the interfaces its agents work through from task experience. Alongside the release, Simular published the paper "Evolving Agent Interfaces". The new model sets a new open-source state of the art on the OSWorld V2 benchmark, achieving a score of 21.3%.

## 🧩 Agent S4 and Evolving Interfaces

Agent S4 is the latest iteration of Agent S, an open-source computer-use agent framework from Simular. While the base framework looks at the screen to complete tasks by clicking, typing, and scrolling in ordinary desktop and web apps, Agent S4 specifically functions as a scientist that evolves the interfaces its agents work through.

## 📊 Performance on OSWorld V2

The performance of Agent S4 is measured on OSWorld V2, a benchmark scored as a strict binary pass/fail with no partial credit. The 21.3% score reflects the difficulty of the benchmark rather than low reliability. 

| Model/Agent | OSWorld V2 Score | Notes |
| :--- | :--- | :--- |
| Agent S4 (Qwen3.8-27B) | 21.3% | New open-source state of the art |
| GPT-5.5 | 13.0% | Exceeds Agent S4 performance |
| Claude Opus 4.8 | 20.6% | Exceeds Agent S4 performance |

With the Qwen3.8-27B model, Agent S4 performs 3.8 times better than the same model with fixed interfaces. It outperforms GPT-5.5 and Claude Opus 4.8 at a fraction of their cost.

## 📜 Research and Papers

Simular has a strong track record in computer-use agents, with several recent academic contributions:

*   **Agent S4**: The paper "Evolving Agent Interfaces" accompanies the new release.
*   **Agent S3**: The paper "Scaling Agents for Computer Use" is accepted to TMLR 2026. Agent S3 set a new SOTA of 69.9% on OSWorld (approaching 72% human performance) and is the first to surpass human-level performance on OSWorld with a score of 72.60%.
*   **Agent S2**: The paper is accepted to COLM 2025. It set new SOTA results on OSWorld, WindowsAgentArena, and AndroidWorld.
*   **Agent S**: The paper was accepted to ICLR 2025 and won the Best Paper Award at the ICLR 2025 Agentic AI for Science Workshop.

## 🚀 Availability and Ecosystem

Agent S runs on macOS, Windows, and Linux. Simular has made several releases of the `gui-agents` library to support these environments:

*   **v0.1.0**: Supported Mac, OSWorld, and WindowsAgentArena.
*   **v0.1.2**: Added support for Linux and Windows.
*   **v0.2.0**: Released alongside Agent S2, described as the new state-of-the-art for computer use agents (CUA), outperforming OpenAI's CUA/Operator and Anthropic's Claude 3.7 Sonnet Computer-Use.
*   **v0.2.5**: Released Agent S2.5, described as simpler, better, and faster, achieving a new SOTA on OSWorld-Verified.

In addition to the agent framework, Simular offers the Simular API, described as an autonomous computer API for building always-on agents. The Simular Platform is noted for world-leading agent infrastructure with 90% token saving. A separate agent, "Sai", is noted as topping OSWorld 2.0, beating GPT and Opus with lower costs (73%).

#Simular #AgentS4 #ComputerUse #OSWorld #OpenSource

---

*Source: [vstorm-co/pydantic-ai-backend](https://github.com/vstorm-co/pydantic-ai-backend)*
*Source: [simular-ai/Agent-S](https://github.com/simular-ai/Agent-S)*
