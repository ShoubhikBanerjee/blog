---
title: "Researchers Introduce CARTBench to Evaluate Performance Gaps in LLM Shopping Assistants"
slug: "researchers-introduce-cartbench-to-evaluate-performance-gaps-in-llm-shopping-assistants"
description: "While large language model (LLM) shopping assistants now recommend products through multi-turn conversations, reliable evaluation has faced obstacles including data scarcity and difficulty..."
date: 2026-11-05T22:04:09+05:30
tags: [LLM, CARTBench, Ecommerce, ArtificialIntelligence, Benchmarking]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# Researchers Introduce CARTBench to Evaluate Performance Gaps in LLM Shopping Assistants

While large language model (LLM) shopping assistants now recommend products through multi-turn conversations, reliable evaluation has faced obstacles including data scarcity and difficulty standardizing criteria. To address these challenges, researchers have introduced CARTBench, a benchmark designed for Complex and Ambiguous Requests with Timelines (CART).

## 🔍 Overview
CARTBench provides a structured approach to assessing shopping assistants by curating cases from real commercial shopping needs across 17 retail domains. The benchmark pairs timestamped dialogues with 1,603 product records to combat data scarcity. To standardize criteria, the system uses case-specific rubrics guided by Ideal Response Principles, which were distilled from manually selected excellent replies from successfully completed orders.

## 🧩 How it works
The evaluation framework is built on several structured components:
*   **Principle-Guided CART Prompting:** A structured recommendation strategy guided by Ideal Response Principles.
*   **Expert-Annotated Criteria:** The benchmark contains 1,328 criteria categorized under Core, Excellence, and Safety.
*   **Frozen Rubrics:** Evaluation is conducted under fixed rubrics to ensure consistency.

## ⚙️ Key details
The researchers evaluated 10 total models, including seven flagship commercial API models such as GPT-6.1-Sol and Claude-Opus-5, as well as open-weight models with 35B+ parameters. The results revealed a significant "understanding-to-execution gap" between required behavior and high-quality purchase advice.

| Category | Performance Metric |
| :--- | :--- |
| Core | 3 of 10 models exceeded 90% |
| Excellence | No models exceeded 45% |

Shared failures were diagnosed in product evidence and unresolved needs, which researchers linked to changing requirements and decisive unknowns during the shopping process.

## 🚀 Availability
Code and data for CARTBench are available at the provided URL. The project is part of arXivLabs, a framework that allows collaborators to develop and share new features on the arXiv website. arXivLabs and its partners adhere to values of openness, community, excellence, and user data privacy.

## 🛠️ Community Features

| Feature | Description |
| :--- | :--- |
| Bibliographic Explorer | What is the Explorer? |
| Connected Papers | What is Connected Papers? |
| Litmaps | What is Litmaps? |
| scite Smart Citations | What are Smart Citations? |
| alphaXiv | What is alphaXiv? |
| CatalyzeX Code Finder for Papers | What is CatalyzeX? |
| DagsHub | What is DagsHub? |
| Influence Flower | What are Influence Flowers? |

#LLM #CARTBench #Ecommerce #ArtificialIntelligence #Benchmarking

---

*Source: [CARTBench: Rubric-Based Evaluation of Shopping Advice for Complex and Ambiguous Requests with Timelines](https://arxiv.org/abs/2611.05862v1)*
