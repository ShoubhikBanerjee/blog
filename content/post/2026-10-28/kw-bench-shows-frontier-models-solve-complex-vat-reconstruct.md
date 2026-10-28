---
title: "kw-bench shows frontier models solve complex VAT reconstruction in minutes"
slug: "kw-bench-shows-frontier-models-solve-complex-vat-reconstruction-in-minutes"
description: "A new benchmark, kw-bench, evaluates coding‑agent harnesses on real‑world investigative knowledge work."
date: 2026-10-28T12:05:05+05:30
tags: [AIbenchmark, knowledgework, frontiermodels, codingagents]
categories: ["AI", "Machine Learning", "AI Agents", "Evaluation", "Knowledge Work"]
author: "Shoubhik Banerjee"
draft: false
---

# kw-bench shows frontier models solve complex VAT reconstruction in minutes

A new benchmark, kw-bench, evaluates coding‑agent harnesses on real‑world investigative knowledge work.

## 🔍 Overview
- Each new generation of frontier model pushes the edge of what is possible.
- A growing body of work treats the coding‑agent harness as infrastructure for knowledge work rather than a coding tool, and a new wave of benchmarks tests it there.
- kw-bench is built from real engagements specialists described to us and focuses on the expensive, investigative part of knowledge work.

## 🧩 Benchmark Design
- First task family: a five‑year VAT reconstruction across three generations of SAP – legacy ECC, a partial S/4HANA migration and a consultant's redesign.
- Input: raw system extracts (page headers, local number formats, partial link tables) with no documentation of how anything connects.
- Grading is deterministic, with no LLM judge.

## ⚙️ Results
| Harness      | Model                 | Score   | Time (minutes) |
|--------------|----------------------|---------|----------------|
| Claude Code  | DeepSeek v4.1 Flash  | 0.00    | 120 (2 hours)  |
| Codex        | DeepSeek v4.1 Flash  | 0.00    | 120 (2 hours)  |
| OpenCode     | DeepSeek v4.1 Flash  | 0.542   | 120 (2 hours)  |
| micro‑cc     | DeepSeek v4.1 Flash  | 0.528   | 120 (2 hours)  |
| micro‑cc     | Claude Opus 5.5      | 0.9986  | 22             |
| Claude Code  | Claude Opus 5.5      | 1.000   | 25             |

- What defeated the two lab harnesses on DeepSeek was inertia: keeping many weak signals alive across a long session.
- On a frontier model the task collapses, delivering near‑perfect scores in a fraction of the time.

## 🚀 Implications
- A weeks‑long engagement now costs minutes and a few dollars.
- Below the frontier, the harness decides how far a model gets; with a matching harness, frontier models achieve essentially perfect performance.
- This highlights the importance of both model capability and harness design for investigative knowledge‑work automation.

## 📊 Scoring Method
- Scores are deterministic; there is no LLM judge involved.
- The benchmark treats the answer as hidden in incomplete and inconsistent evidence that must be recovered and defended to the cent.


#AIbenchmark #knowledgework #frontiermodels #codingagents

---

*Source: [kw-bench: Breaking Frontier Harnesses on Real-World Tasks](https://arxiv.org/abs/2610.36405v1)*
*Source: [Do AI Scientists Know What's New?](https://arxiv.org/abs/2610.36511v1)*
