---
title: "Toby Ord analyzes speed‑focused scaling of AI swarms"
slug: "toby-ord-analyzes-speedfocused-scaling-of-ai-swarms"
description: "AI swarms are being examined as a new lever for speeding up inference, according to a short post by Toby Ord."
date: 2026-10-05T22:07:36+05:30
tags: [AISwarms, InferenceScaling, AIAgents, RSI]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Machine Learning", "AI Safety"]
image: "https://substackcdn.com/image/fetch/$s_!3yYS!,w_1200,h_675,c_fill,f_jpg,q_auto:good,fl_progressive:steep,g_auto/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd6d17996-2bef-40a4-abe3-be72a0e8a227_258x258.png"
author: "Shoubhik Banerjee"
draft: false
---

# Toby Ord analyzes speed‑focused scaling of AI swarms

AI swarms are being examined as a new lever for speeding up inference, according to a short post by Toby Ord.

## 🔍 Overview
- Ord frames AI swarms as “a new form of inference‑scaling.”
- The analysis centres on when you should use swarms, especially when you are in a hurry.

## 🧩 How it works
- Swarms consist of multiple agents that run in parallel.
- A key observation is that “swarms are useful if you’re in a hurry because though they need a ton of tokens relative to single agents, their parallelization lets you get things done in less wall clock time.”
- Quote: “Why would you ever use swarms? The most important answer is speed.”

## ⚙️ Key details
- In a 4‑agent swarm the total token count was about twice that of a single‑agent run, but *per agent* it required only half as many tokens.
- Because the agents run concurrently, “it can theoretically achieve the same task in half the time.”
- Scaling is not linear. Economists’ “stepping on toes” parameter applies: as the number of agents grows, performance gains diminish.
- Ord writes: “This means that scaling up the number of agents in the swarm by 10x doesn’t get as much performance as using 10x as many tokens with one agent. Instead it gets 10λ x as much — which is 3x to 5x.”
- The shortfall “accumulates quickly for larger scale‑ups, with the swarm falling further and further behind.”
- Despite diminishing returns, “swarm scaling is still powerful enough that it suggests swarms could increase the chance of an RSI‑driven intelligence explosion rather than reduce the chance.”
- “I’d hoped that the value of λ for AI agents would be lower, making an intelligence explosion less likely, but that appears to not be the case.”

## 💡 Why it matters
- Agents introduce a new parameter in scaling AI capabilities, complementing the traditional compute‑and‑data approach.
- If coordination among agents improves (e.g., “greater‑than‑sum‑of‑parts” hacks), returns to scaling could rise further.
- The speed advantage and scaling behavior have direct implications for AI safety discussions around rapid self‑improvement (RSI).

#AISwarms #InferenceScaling #AIAgents #RSI

---

*Source: [Import AI 475: Swarm scaling; Google DeepMind watermarks biology; and the AI science economy](https://importai.substack.com/p/import-ai-475-swarm-scaling-google)*
