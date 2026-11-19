---
title: "RoboDx Benchmark Evaluates AI Repair of Robot Navigation Software"
slug: "robodx-benchmark-evaluates-ai-repair-of-robot-navigation-software"
description: "Researchers have introduced RoboDx, a benchmark for evaluating how well AI models can diagnose and repair faults in simulated robot navigation software. The benchmark reveals that passing unit tests..."
date: 2026-11-19T18:06:46+05:30
tags: [RoboDx, RobotNavigation, AIBenchmark, SoftwareRepair, ClaudeOpus, DiagnosticAI]
categories: ["AI", "Machine Learning", "Robotics", "Software Engineering", "AI Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# RoboDx Benchmark Evaluates AI Repair of Robot Navigation Software

Researchers have introduced RoboDx, a benchmark for evaluating how well AI models can diagnose and repair faults in simulated robot navigation software. The benchmark reveals that passing unit tests does not guarantee correct robot behavior, and that even verified repairs often fail to address all injected faults — especially undocumented configuration constants.

## 🔍 Overview
- RoboDx generates repair tasks for simulated robot navigation software with known injected faults
- Includes 100 tasks in the RoboDx-Hard-100 set
- Features a hidden verifier that only marks repairs verified if the robot drives correctly in hidden scenarios the agent never sees
- Contains two evaluation tracks: one with code visible, another where code is hidden and the agent must pick the cause from a list of hypotheses

## 🧩 How It Works
- **Hidden verification**: A repair is marked verified only if the robot drives correctly in hidden scenarios not shown to the agent
- **Two-fault tasks with quiet faults**: A quiet fault makes no hidden scenario fail unless the other fault is also present
- **Diagnostic track**: Models receive measurements from the faulty robot, selected so only the true cause produces all of them in the simulator
- **Hypothesis selection**: When code is hidden, agents choose from a list of hypothesized causes

## ⚙️ Key Details
| Aspect | Detail |
|--------|--------|
| Total tasks analyzed | 94 |
| Single-fault tasks | 44 |
| Two-fault tasks | 50 |
| Verified repairs by Claude Opus 5.5 (two-fault tasks) | 49 of 50 |
| Verified repairs removing both injected edits | 17 of 49 |
| Opus naming both faults without seeing code | 10 of 50 |
| Models naming true cause from measurements (max) | 38 of 94 |
| Models with simulator output for every hypothesis | Right on almost all |
| Gain from models' own predictions of simulator output | No detectable gain |
| Real bug-fix PR tasks evaluated | 97 |

- Most faults left behind after verified repairs are configuration constants whose correct values the task documentation does not state
- On real bug-fix pull requests, Claude Haiku 5.5 scored lowest among four models tested; the other three models showed no clear ordering

## 💡 Why It Matters
- Unit tests alone are insufficient for validating robot navigation repairs
- Verification via hidden driving scenarios catches patches that pass unit tests but drive the robot off course
- Even when repairs pass verification, they frequently fail to fix all faults — particularly undocumented configuration values
- Diagnostic ability from raw measurements remains limited across current models
- Access to simulator outputs for hypotheses dramatically improves diagnostic accuracy, but models' own predictions provide no benefit

#RoboDx #RobotNavigation #AIBenchmark #SoftwareRepair #ClaudeOpus #DiagnosticAI

---

*Source: [RoboDx: Repair and Diagnosis of Faults in Robot Software](https://arxiv.org/abs/2611.23816v1)*
