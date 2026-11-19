---
title: "Databricks introduces Unity Gateway Insights for AI agent trace analysis"
slug: "databricks-introduces-unity-gateway-insights-for-ai-agent-trace-analysis"
description: "Databricks has introduced Unity Gateway Insights, a feature that automatically uses Genie to analyze millions of agent traces alongside business data and ontology to identify where tokens are being..."
date: 2026-11-19T06:12:23+05:30
tags: [Databricks, UnityGateway, AIagents, MCP, Tokenomics, Observability]
categories: ["AI", "AI Agents", "Enterprise Software", "Cloud Infrastructure", "Data & Analytics"]
image: "https://www.databricks.com/sites/default/files/2026-11/2026-11-Blog-Introducing-Unity-Gateway-Insights-1200x628-2x.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks introduces Unity Gateway Insights for AI agent trace analysis

Databricks has introduced Unity Gateway Insights, a feature that automatically uses Genie to analyze millions of agent traces alongside business data and ontology to identify where tokens are being wasted.

## 🧩 How it works
Unity Gateway Insights runs an investigation developed during the rollout of coding agents to thousands of Databricks engineers. The process involves:
- Sampling sessions and grouping them into workstreams by kind of work.
- Checking each workstream for failing MCP tools, bloated context, frontier models on simple tasks, and repeated workflows.
- Ranking findings by the tokens at stake.

The system identifies specific inefficiencies, such as simple prompts being routed to expensive models or recurring MCP errors. Findings link to example sessions, allowing users to open the traces behind each issue. Users can add up to 10 custom questions to a report, such as whether the newest model is worth it for their team or which MCP server wasted the most tokens.

## ⚙️ Key details
The evidence highlights several specific operational insights and capabilities:
- **Cost Recovery**: Fixing common MCP errors recovered an estimated $1.2M in costs a year.
- **Model Selection**: Offline replays showed no performance gain from upgrading from Opus 4.8 to Opus 5, leading to a decision to stay on the cheaper 4.8 model.
- **Smart Routing**: Traces showed that simple prompts were going to expensive models, prompting the adoption of Smart Routing.
- **Data Requirements**: Finding waste requires a full record of every step of every agent session, including inputs/outputs, tool calls, subagents, intermediate steps, latency, and token cost. A standalone gateway records only requests passing through it; capturing the rest requires instrumenting every coding agent and exporting traces to a data platform.

## 🚀 Availability
To access the feature, users with traffic flowing through Unity Gateway can navigate to **AI Gateway > Observability > Insights**. From there, they can generate a report for the last day, 7 days, or 30 days. The Insights feature then writes a report on the tokenomics of the coding agent rollout, answering predefined and custom questions.

#Databricks #UnityGateway #AIagents #MCP #Tokenomics #Observability

---

*Source: [Introducing Unity Gateway Insights](https://www.databricks.com/blog/introducing-unity-gateway-insights)*
