---
title: "Dogwood Local Engine released as Apache‑2.0 library for temporal policy enforcement"
slug: "dogwood-local-engine-released-as-apache2-0-library-for-temporal-policy-enforcement"
description: "Today we are releasing the Dogwood Local Engine under the Apache 2.0 license. The engine embeds the Dogwood governance language to enforce agent actions with temporal conditions."
date: 2026-10-01T18:04:45+05:30
tags: [Dogwood, AIAgents, OpenSource, PolicyEngine]
categories: ["AI", "AI Agents", "Software Engineering", "Open Source", "Systems"]
image: "https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/29/Screenshot-2026-09-29-at-1.23.31 PM-1156x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# Dogwood Local Engine released as Apache‑2.0 library for temporal policy enforcement

Today we are releasing the Dogwood Local Engine under the Apache 2.0 license. The engine embeds the Dogwood governance language to enforce agent actions with temporal conditions.

## 🔍 Overview
- Dogwood is an open source governance language for agents and their actions, released in August.
- Policies specify which actions an agent may take and under what conditions, including temporal conditions that refer to past actions and outcomes.

## 🧩 How it works
- The engine can be embedded as a library into an enforcement layer that regulates agents’ tool calls.
- It maintains a durable record of past actions, tracking the order, timing, and outcomes so it can survive crashes and restart.
- Only request events receive allow/deny verdicts; response events record outcomes (e.g., test pass/fail) used by temporal clauses.
- An event is a timestamped record of one step of a tool call. A tool call typically generates a request event and a response event, forming the history evaluated by the engine.

## ⚙️ Key details
- Supports dynamic policy updates without pausing workflows.
- Example policies:
  - `run_tests`: the agent may always run the tests.
  - `push_after_green_tests`: the agent may push only when a test run has passed within the last fifteen minutes and no run has failed since. The `when` temporal clause expresses this condition.
- The temporal clause is evaluated against the event history; it depends on events that happened before the request.

## 🚀 Availability
- Released under the Apache 2.0 open source license.
- Available as a local engine library that can be embedded.

## 💡 Why it matters
- Allows policies to depend on past actions, their outcomes, order, and timing.
- Guarantees enforcement after crashes because the engine stores history durably.
- Supports policy changes during a session without stopping the workflow.

#Dogwood #AIAgents #OpenSource #PolicyEngine

---

*Source: [Introducing the Dogwood Local Engine: temporal governance for agent actions | Amazon Web Services](https://aws.amazon.com/blogs/opensource/introducing-the-dogwood-local-engine-temporal-governance-for-agent-actions/)*
