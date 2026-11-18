---
title: "Output-Side Compression Model Achieves High Code Fidelity and Low Token Usage"
slug: "output-side-compression-model-achieves-high-code-fidelity-and-low-token-usage"
description: "A new development in output-side compression has been released. It achieves high code fidelity while reducing token usage significantly."
date: 2026-11-18T06:16:59+05:30
tags: [AI, MachineLearning, CodeGeneration, Optimization]
categories: ["AI", "Machine Learning", "AI Agents", "Software Engineering", "Optimization"]
image: "https://avatars.githubusercontent.com/u/104168679?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Output-Side Compression Model Achieves High Code Fidelity and Low Token Usage

A new development in output-side compression has been released. It achieves high code fidelity while reducing token usage significantly.

## 🔍 Overview
The development is described as "Brain big. Mouth small." It is measured against reference answers, not base Gemma. The entire project cost under five dollars and fifty minutes of GPU time.

## 🧩 How it works
The system takes 185 tokens in and outputs 56. It preserves meaning at 0.91–0.98 cosine. It works by answering questions with about a quarter fewer tokens than verbose reference answers.

## ⚙️ Key details
*   **Code Fidelity:** Code fences are reproduced byte-exact 96–100% of the time. Identifiers, error strings, CLI commands, and code never move.
*   **Configuration:** It requires no skill file, no system prompt, and no `/caveman` toggle.
*   **Variants:** There are two flavors, selected by VRAM.
*   **Metrics:** Every number mentioned falls out of `eval/metrics.py`.

## 🚀 Availability
You can rebuild it today. It reaches places a system prompt cannot, such as embedded hosts, third-party agent frameworks, and any environment that owns its own prompt template.

#AI #MachineLearning #CodeGeneration #Optimization

---

*Source: [JuliusBrussee/cavegemma](https://github.com/JuliusBrussee/cavegemma)*
