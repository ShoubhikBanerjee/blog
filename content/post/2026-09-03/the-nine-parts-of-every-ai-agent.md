---
title: "The nine parts of every AI agent"
description: "Every AI agent, from vendor demos to internal prototypes, is built from the same nine components. These parts define how agents operate, interact, and deliver results in commercial environments."
date: 2026-09-03T22:06:46+05:30
tags: [AIagents, memory, contextengineering, runtime, MCP, commercialAI]
categories: [AI]
image: "https://media.licdn.com/dms/image/v2/D4E12AQELmTkGoLlSRA/article-cover_image-shrink_720_1280/B4EaBji5L9G4AU-/0/1788376493682?e=2147483647&v=beta&t=bTsFofTp03pYDglgogaxRdQlubaqaNqTczQCKkLb_iY"
author: "Shoubhik Banerjee"
draft: false
---

# The nine parts of every AI agent

Every AI agent, from vendor demos to internal prototypes, is built from the same nine components. These parts define how agents operate, interact, and deliver results in commercial environments.

## 🧩 The nine parts

- **Memory**: Everything the agent knows about you and your work that wasn't in the message you just sent it. For commercial work, this includes project records like subcontract packages, marked-up drawings, diary entries, labour returns, early warnings, and correspondence.
- **Context engineering**: Choosing the relevant slice of memory for the task at hand. Giving the AI everything produces a worse answer, more slowly, at higher cost.
- **Skills**: A complete piece of work the agent knows how to do end to end, in the right order, with judgement calls marked. Writing one out properly takes about an hour and provides inputs, steps, judgement calls, and what a good output looks like.
- **Tools**: How the agent reaches the outside world. MCP (Model Context Protocol) is the standard that lets a model connect to a live system and read from it directly.
- **Systems**: A commercial agent needs five systems, four vendors, and often a shared drive with folders named "FINAL v3 USE THIS ONE".
- **Data extraction**: For each record, name the system it lives in, then ask whether data comes out of it any way other than someone exporting to Excel on a Friday. Where the answer is no, that is the bottleneck.
- **Runtime**: The loop where the agent plans, acts, looks at what came back, adjusts, retries when something fails, and keeps going until the job is done. Assessing an event isn't one question, it's fifteen in sequence, with answers changing subsequent questions.
- **Triggers**: What start the work without anyone asking. The most obviously valuable part, because most commercial issues arise from someone not looking on the right day.

## ⚙️ Key details

- Memory already exists somewhere, either as a diary submitted through a system or a scanned signed sheet in a folder. Getting it across that line costs money.
- A short list of relevant context is a rule you can hand over, and it's the difference between an agent that answers in seconds for pennies and one that takes a minute and costs more to be less accurate.
- Products with a real runtime have a clear answer. Products without one change the subject to the quality of their model.
- In every case, somebody knew the rule for triggers.

#AIagents #memory #contextengineering #runtime #MCP #commercialAI

---

*Source: [How to build any AI agent](https://www.linkedin.com/pulse/how-build-any-ai-agent-william-doyle-mrics-tvrxe)*
