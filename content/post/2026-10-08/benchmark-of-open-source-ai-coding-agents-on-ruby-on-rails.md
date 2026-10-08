---
title: "Benchmark of Open-Source AI Coding Agents on Ruby on Rails"
slug: "benchmark-of-open-source-ai-coding-agents-on-ruby-on-rails"
description: "The Rails Foundation commissioned a benchmark of AI coding agents on real‑world Rails projects."
date: 2026-10-08T22:04:21+05:30
tags: [Rails, AIAgents, Benchmark]
categories: ["AI", "Artificial Intelligence", "Software Engineering", "Machine Learning"]
image: "https://evilmartians.com/social-cards/events/agents-on-rails-deccan-queen.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Benchmark of Open-Source AI Coding Agents on Ruby on Rails

The Rails Foundation commissioned a benchmark of AI coding agents on real‑world Rails projects.

## 🔍 Overview
- 41 tasks on Writebook and Fizzy
- 17 models evaluated
- 1,770 runs performed
- All code and data are open source

## 📊 Benchmark Details
- The hardest part was building a test the best models cannot max out
- Result: 35% of runs reached Stage 2

## ⚙️ Harness
- Built and open‑sourced a benchmarking harness called `rails/lemans`

## 🚀 How to Use
- You can point the harness at any repository; the best test suite is always your own codebase

## 💡 Findings
- Models never reach for **delegated_type** or **purge_later**
- They are the worst of all at **migrations** and **i18n**
- Plenty of other surprises were observed

| Feature | Model Performance |
|---------|--------------------|
| delegated_type | Never reached |
| purge_later | Never reached |
| migrations | Worst of all |
| i18n | Worst of all |


![figure](https://evilmartians.com/static/f6aaeef3931836d11bc64a42fed14bf0/cover.jpg?v=5c8c3153)

![figure](https://evilmartians.com/static/d8631a7a39a0e8297e2f17395922b711/cover.png?v=840f2fbd)

![figure](https://evilmartians.com/static/7b9c1ab8522d661cc03a32443bdd3377/cover.png?v=e04d41b2)

#Rails #AIAgents #Benchmark

---

*Source: [Agents on Rails: learnings from benchmarking AI models for the Rails Foundation by Evil Martians](https://evilmartians.com/events/agents-on-rails-deccan-queen)*
