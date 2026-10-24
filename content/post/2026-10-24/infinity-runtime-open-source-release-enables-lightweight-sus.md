---
title: "Infinity Runtime Open‑Source Release Enables Lightweight, Suspended AI Agents"
slug: "infinity-runtime-opensource-release-enables-lightweight-suspended-ai-agents"
description: "Infinity, a new research runtime for AI agents, is now released under the Apache 2.0 license as part of the Hydro project, a joint effort between AWS and UC Berkeley."
date: 2026-10-24T12:01:24+05:30
tags: [AIAgents, InfinityRuntime, ServerlessAI]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Serverless Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/10/21/Screenshot-2026-10-21-at-4.13.06 PM-1160x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# Infinity Runtime Open‑Source Release Enables Lightweight, Suspended AI Agents

Infinity, a new research runtime for AI agents, is now released under the Apache 2.0 license as part of the Hydro project, a joint effort between AWS and UC Berkeley.

## 🔍 Overview
- Traditional agent harnesses run a **blocking loop**: call the model, invoke a tool, wait for the tool to return, then repeat.
- While waiting, the agent **holds a process and its memory** and cannot handle new events.
- Typical wait times include a 20‑minute build for a coding agent, hours for a triage agent to see a new pull request, or an overnight pause for an assistant awaiting approval.

## 🧩 How it works
- Infinity applies the same principles that modern programming languages use for **asynchronous functions** (`async`/`await`).
- When an agent calls a tool, Infinity:
  1. **Dispatches** the tool call.
  2. **Saves** the conversation history (the complete state needed to resume).
  3. **Suspends** the agent.
- When the tool result arrives, the runtime **loads the saved history** and **resumes** the agent from that point.
- Execution is broken into **bounded slices**:
  * Load history from a pluggable store.
  * Run one model completion.
  * Persist the output.
  * Dispatch at most one tool call.
  * End the slice.
- Tool calls act as **await points**; a slice never blocks for a tool, timer, or other external operation.
- All resumable events (user text, tool results) are delivered via a **shared input queue**.

### State‑saving techniques (context for Infinity)
| Technique | Memory behavior |
|-----------|-----------------|
| OS threads / stackful coroutines | Keep the task’s entire call stack in memory while it waits |
| Stackless coroutines (e.g., Rust `async fn`) | Compiler transforms the function into a state machine that holds only the values needed at each `await`, giving a smaller memory footprint |

## ⚙️ Key details
- **Open source**: Released under the Apache 2.0 license.
- **Collaboration**: Developed by AWS and UC Berkeley as part of the Hydro project.
- **Lightweight concurrency**: 75,000 concurrent agents can fit in the 8 GB RAM of a Raspberry Pi 5.
- **Serverless friendly**: When an agent is suspended, the serverless function can terminate, so even multi‑day tool calls consume no compute while waiting.
- **Early research release**: Intended to gather early feedback from the community.

## 🚀 Availability
Infinity is publicly available today as an open‑source project under the Apache 2.0 license. It can be integrated with standard serverless platforms and any pluggable storage for persisting conversation history.

## 💡 Why it matters
- Eliminates the **idle waiting** problem that forces agents to hold resources without doing work.
- Enables **massive scaling** of agents on modest hardware and serverless environments.
- Leverages proven async patterns from languages like Rust, JavaScript, and Python, offering a proven path to efficient, resumable AI agent workloads.


![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/10/21/Fig1infinity.png)

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/10/21/Fig3Infinity.png)

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/10/21/image_1024.png)

#AIAgents #InfinityRuntime #ServerlessAI

---

*Source: [Introducing Infinity: a runtime for extreme agent concurrency | Amazon Web Services](https://aws.amazon.com/blogs/opensource/introducing-infinity-a-runtime-for-extreme-agent-concurrency/)*
