---
title: "IBM’s CUGA Harness Outperforms Others in AppWorld Agent Benchmark"
slug: "ibms-cuga-harness-outperforms-others-in-appworld-agent-benchmark"
description: "We evaluated three agent harnesses on the AppWorld benchmark using the same open‑weight model and found that the choice of harness moved task completion rates from as low as 30 % to as high as 81 %."
date: 2026-11-03T22:02:32+05:30
tags: [AIAgents, AgentHarness, Benchmark, EnterpriseAI]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Machine Learning", "Enterprise Software"]
image: "https://cdn-uploads.huggingface.co/production/uploads/636c2b3c1df179e8b83d7730/HAejcV9UI0kFWjSLj5Hva.png"
author: "Shoubhik Banerjee"
draft: false
---

# IBM’s CUGA Harness Outperforms Others in AppWorld Agent Benchmark

We evaluated three agent harnesses on the AppWorld benchmark using the same open‑weight model and found that the choice of harness moved task completion rates from as low as 30 % to as high as 81 %.

## 🔍 Overview
- Nearly 200 agent harnesses are available for building generalist AI agents.
- Changing only the harness can dramatically affect performance, as shown by a jump from 23 % to 52 % on SWE‑bench Pro with the same GLM‑5.2 model.

## ⚙️ Experimental Setup
- **Model**: GLM‑5.3‑flash (open‑weight) used for every run.
- **Tasks**: 90 AppWorld tasks across 30 scenarios (one attempt per task).
- **Benchmark**: AppWorld – multi‑step tasks spanning 9 apps and 457 APIs (email, payments, file storage, etc.).
- **Evaluation**: Harbor framework; public setup in the `harbor-eval` fork.
- **Consistency Rule**: A scenario passes only when all three of its variants pass, rewarding consistent performance.
- **Limitations**: Results are from a 90‑task sample on a single benchmark and did not include policy enforcement.

## 📊 Results
- Overall task completion varied widely by harness:
  - From 30 % (lowest) to 81 % (highest) when only the harness changed.
- Scenario‑level gaps (number of scenarios where the harness lagged):
  - CUGA: 20 scenarios
  - Hermes: 8 scenarios
  - Deep Agents: 2 scenarios
- The same GLM‑5.2 model improved from 23 % to 52 % on SWE‑bench Pro when the harness changed.

## 🛠️ Harness Details
| Harness | Primary Use | Notable Features |
|---|---|---|
| **CUGA** (ConfigUrable Generalist Agent) | General‑purpose agent for enterprise deployments | Open‑source, works with open‑weight or hosted models, runs inside sovereign or air‑gapped environments, includes a policy layer that moves business rules out of prompts into the harness |
| **Hermes** (Nous Research) | Always‑on personal assistants | Designed for continuous, conversational assistance |
| **Deep Agents** (LangChain) | Long, multi‑step tasks such as research | Optimized for extended, chained reasoning workflows |

## 💡 Why It Matters
- The harness is a critical component; it can catch mistakes before they affect results, reducing the number of model decisions required.
- Enterprise teams can encode business rules (e.g., payment approval, PII protection) as **policies** in the harness rather than relying on prompts, which are only instructions, not enforcement.
- CUGA’s policy layer, described in the ACM CAIS 2026 paper *Governance by Construction for Generalist Agents* (arXiv), demonstrates a concrete way to separate guidance from enforcement.
- The ability to deploy the harness inside an organization’s own boundary (including sovereign clouds and air‑gapped systems) addresses enterprise concerns that benchmark suites do not test.

*These findings highlight that selecting the right agent harness is as important as choosing the underlying model, especially for mission‑critical enterprise applications.*

![figure](https://cuga-project.github.io/cuga-artifacts/images/cuga-policy-playground.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6806091ee92bd22fd8ce9719/P6P8ZzHR8yL7GOOO4hQOg.png)

#AIAgents #AgentHarness #Benchmark #EnterpriseAI

---

*Source: [Same Model, Different Harness: CUGA, Hermes, and Deep Agents — When to Pick CUGA?](https://huggingface.co/blog/ibm-research/cuga-harness)*
