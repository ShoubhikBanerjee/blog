---
title: "EvalView 0.9.0 introduces offline regression testing for AI agents"
slug: "evalview-0-9-0-introduces-offline-regression-testing-for-ai-agents"
description: "EvalView 0.9.0 has been released, introducing a tool for regression testing AI agents that operates offline without requiring paid API credentials or making paid inference calls. The release focuses..."
date: 2026-11-20T18:09:02+05:30
tags: [EvalView, AIagents, RegressionTesting, LangGraph, CI, LLMops]
categories: ["AI", "AI Agents", "Software Testing", "DevOps", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/31502796?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# EvalView 0.9.0 introduces offline regression testing for AI agents

EvalView 0.9.0 has been released, introducing a tool for regression testing AI agents that operates offline without requiring paid API credentials or making paid inference calls. The release focuses on capturing agent behavior to detect regressions in CI pipelines, distinct from observability platforms or metric scoring tools.

## 🔍 Overview
EvalView is designed to address the gap between passing tests and user experience by snapshotting an agent's behavior—specifically which tools it calls, in what order, and with what output. It flags any drift from recorded baselines, functioning as a merge-time regression gate. This approach inverts the traditional evaluation model by recording what an agent actually does now and flagging deviations, rather than requiring developers to pre-define assertions, metrics, or rubrics for "good" behavior.

## 🧩 How it works
The core workflow involves taking a snapshot of the agent's current behavior. When new behavior is confirmed to be correct, developers can accept it as the new baseline using `evalview snapshot`, similar to updating snapshots in Jest. The deterministic tool and sequence diff runs offline, meaning it does not require an API key for the regression check. Additional capabilities are opt-in:
*   **LLM Judge:** Available when output-quality scoring is desired.
*   **Semantic Comparison:** Embedding-based comparison can be enabled as an opt-in feature.
*   **API Usage:** EvalView 0.9.0 utilizes the Responses API.

## ⚙️ Key details
EvalView is compatible with LangGraph, CrewAI, OpenAI, and Anthropic. It is positioned differently from other tools in the ecosystem:

| Category | Tools Mentioned | Function |
| :--- | :--- | :--- |
| Observability | Langfuse, LangSmith | Visibility into agent operations |
| Metric Scoring | promptfoo, DeepEval, Braintrust | Scoring based on predefined metrics |
| Regression Gate | EvalView | Flags drift from recorded behavior baselines |

Many teams utilize one of the observability or scoring tools for visibility alongside EvalView as a strict regression gate. The tool ensures that while unit tests may pass, behavioral regressions are caught before users notice them.

## 🔒 Telemetry and Privacy
The installed CLI sends anonymous usage events to PostHog when specific tracked commands are executed. These events use a random installation ID and include the EvalView version, command, runtime, CI environment, and aggregate outcomes. The system explicitly excludes prompts, tool arguments, outputs, paths, and repository names from these events. Developers can opt out of telemetry by setting `EVALVIEW_TELEMETRY_DISABLED=1` before first use or by running `evalview telemetry off`.

## 💡 Why it matters
Traditional evaluation tools often require manual definitions of success criteria. By automating the baseline recording process, EvalView simplifies the regression testing workflow for AI agents. Because the primary diffing process runs offline without paid inference, it offers a cost-effective way to maintain agent reliability in continuous integration environments, with GitHub runner usage billed separately from the tool itself.

#EvalView #AIagents #RegressionTesting #LangGraph #CI #LLMops

---

*Source: [hidai25/eval-view](https://github.com/hidai25/eval-view)*
