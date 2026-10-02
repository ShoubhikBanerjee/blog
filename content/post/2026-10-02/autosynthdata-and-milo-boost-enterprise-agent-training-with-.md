---
title: "AutoSynthData and MILO Boost Enterprise Agent Training with Automated Data Generation"
slug: "autosynthdata-and-milo-boost-enterprise-agent-training-with-automated-data-generation"
description: "ServiceNow CoreAI announced an update to its AutoSynthData pipeline and introduced the MILO framework for automatically generating training data and evolving agent harnesses in enterprise..."
date: 2026-10-02T18:04:26+05:30
tags: [EnterpriseAI, AutoSynthData, MILO, AITraining, AgenticSystems]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Machine Learning", "Enterprise Software"]
image: "https://cdn-uploads.huggingface.co/production/uploads/68642da9885da181fde1ad70/8kSzlHLOdu5hchCtPnK8D.png"
author: "Shoubhik Banerjee"
draft: false
---

# AutoSynthData and MILO Boost Enterprise Agent Training with Automated Data Generation

ServiceNow CoreAI announced an update to its AutoSynthData pipeline and introduced the MILO framework for automatically generating training data and evolving agent harnesses in enterprise environments.

## 🔍 Overview
- Enterprises need agents that work well in their own environments.
- The work they ask these agents to do is shaped by the systems they use, the rules they follow, and the state of their data.
- A model may be broadly capable and still struggle with a particular environment: a workflow it handles poorly, a combination of tools it misuses, or a constraint it fails to respect.
- The difficulty is turning those weaknesses into training data.

## 🧩 How AutoSynthData Works
- AutoSynthData uses a target model’s failures and a stronger teacher’s successes to decide what the model should learn next, then generates and validates new tasks that exercise those capabilities.
- It first evaluates the target model in the environment using diagnostic tasks and identifies patterns in the tasks it struggles to complete.
- A stronger teacher helps characterise which of those tasks are solvable and what successful behaviour looks like.
- AutoSynthData turns the resulting capability gaps into new executable tasks, checks each task in the environment, and uses accepted samples for post‑training.
- As the model improves, the curriculum shifts toward what it still finds difficult.

## ⚙️ Key Details of Task Definition
- **Task abstraction**: task = (system specification, user prompt, verifier).
- **System specification** defines constraints, environment policies, and task‑specific initialisation; it must be compatible with the environment’s tools, state, and supported actions.
- **User prompt** specifies the user’s goal and any user‑level constraints.
- **Verifier** determines whether the resulting trajectory successfully completes the task.
  - *Consistency*: agrees with the user prompt, system specification, and environment state.
  - *Soundness*: rejects trajectories that fail to satisfy the task or violate constraints.
  - *Completeness*: accepts valid solutions rather than encoding a single reference trajectory.
- **Task properties for training**:
  - *Feasibility*: at least one trajectory exists that satisfies the prompt while respecting the specification.
  - *Realism*: the prompt should resemble something a user would plausibly ask in the target environment.
  - *Difficulty*: the task should expose a weakness of the current agent.
- A lax verifier can reward incorrect behaviour, while an overly restrictive verifier can penalise valid solutions.

## 🚀 MILO Framework and Results
- MILO (Meta‑evolutionary Island Orchestration) co‑evolves agent harnesses and the discovery strategy.
- It combines:
  1. Hierarchical lineage memory over island‑based trees, using rejected mutations as negative evidence.
  2. Per‑island mutator agents that rewrite complete harnesses using global search history and parent‑specific feedback.
  3. An orchestrator that adapts search through lineage grafting, speciation, mutator reassignment, and curriculum revision.
- Across Terminal‑Bench 2.1, PaperBench, and DeepSWE, MILO‑discovered harnesses outperform eight state‑of‑the‑art harnesses and six search methods using frontier (Opus 4.8) and open‑weight (gpt‑oss‑120b) models.
- With Opus 4.8, MILO improves resolution over its initial harness by **+12.0 %**, **+28.3 %**, and **+10.3 %** respectively, compared with best prior‑search gains of **+4.5 %**, **+18.3 %**, and **0 %**.
- On Terminal‑Bench 2.1, MILO achieves **86.1 ± 2.0 %**, exceeding the official leaderboard’s top entry (**83.8 ± 2.3 %**) while using **26 % fewer tokens** than its initial harness.
- On EinsteinArena open problems, MILO improves best‑known upper bounds for Erdős minimum‑overlap (0.3808586 → 0.3808568) and the first and third autocorrelation inequalities (1.50274365 → 1.50274360; 1.45081 → 1.44889).

| Benchmark            | MILO Gain (Opus 4.8) | Prior Best Gain |
|----------------------|---------------------|-----------------|
| Terminal‑Bench 2.1   | +12.0 %             | +4.5 %          |
| PaperBench           | +28.3 %             | +18.3 %         |
| DeepSWE              | +10.3 %             | 0 %             |

## 💡 Why It Matters
- Turning observed capability gaps into concrete training data enables systematic improvement of enterprise agents.
- The curriculum automatically focuses on the remaining weak spots, reducing manual data engineering.
- MILO’s evolutionary search yields harnesses that achieve higher performance with fewer computation tokens, demonstrating efficient scaling for large language models in real‑world enterprise settings.


![figure](https://cdn-uploads.huggingface.co/production/uploads/68642da9885da181fde1ad70/mlI168havBLGXY2qbd4ud.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/66a41f3c1d52bffc13c285a5/sM50frTSx9Q7Yyh6UNcGz.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/66a41f3c1d52bffc13c285a5/huMlVCBcc-IseCIk5uEIJ.png)

#EnterpriseAI #AutoSynthData #MILO #AITraining #AgenticSystems

---

*Source: [AutoSynthData: Generating Training Data for Enterprise Agents](https://huggingface.co/blog/ServiceNow-AI/autosynthdata)*
*Source: [MILO: Automated Harness Discovery via Orchestrated Multi-Agent Evolution](https://arxiv.org/abs/2609.38349v1)*
