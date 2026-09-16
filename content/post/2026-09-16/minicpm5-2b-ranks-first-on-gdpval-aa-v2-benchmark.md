---
title: "MiniCPM5-2B Ranks First on GDPval-AA v2 Benchmark"
slug: "minicpm5-2b-ranks-first-on-gdpval-aa-v2-benchmark"
description: "MiniCPM5-2B has achieved the top score on the GDPval-AA v2 benchmark, which measures models on real-world work tasks against a human baseline of 1,000."
date: 2026-09-16T22:05:42+05:30
tags: [MiniCPM52B, LLM, OpenWeight, Benchmarks]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Open Source Software"]
image: "https://uploads.sitepoint.com/wp-content/uploads/medium_minicpm5_2b_benchmark_analysis_e3ba57ccd9.webp"
author: "Shoubhik Banerjee"
draft: false
---

# MiniCPM5-2B Ranks First on GDPval-AA v2 Benchmark

MiniCPM5-2B has achieved the top score on the GDPval-AA v2 benchmark, which measures models on real-world work tasks against a human baseline of 1,000.

## 📊 Performance Benchmarks

On the GDPval-AA v2 benchmark, MiniCPM5-2B scored 831, placing it first. It outperformed Ling 3.0 Tiny by 113 Elo and Granite 4.2 8B by 183 Elo. On the AA-Briefcase agentic knowledge work benchmark, it ranked second with a score of 438.

| Model | GDPval-AA v2 Score | AA-Briefcase Score | Intelligence Index |
| :--- | :--- | :--- | :--- |
| MiniCPM5-2B | 831 | 438 | 15 |
| Ling 3.0 Tiny | 718 | 485 | 16 |
| Granite 4.2 8B | 648 | 331 | 14 |
| Gemma 4 12B | 593 | Not stated | 16 |
| Qwen3.5 9B | 590 | Not stated | 15 |
| Granite 4.2 3B | Not stated | 134 | 11 |

## ⚙️ Key Details

MiniCPM5-2B is a dense causal language model based on the standard LlamaForCausalLM layout. Its technical specifications include:

* **Parameters:** 1.98 billion non-embedding parameters (2.6 billion total).
* **Architecture:** 42 layers deep with grouped-query attention across 16 query heads and 2 key-value heads.
* **Context Length:** 131,072 tokens.
* **Licence:** Apache-2.0.

## 💡 Why it Matters

MiniCPM5-2B is the smallest model in its field and sits on the maximum capability density envelope, which corresponds to a doubling time of roughly 3.5 months. It is the first among open-weight models under 4B parameters on the Intelligence Index v4.2. 

Efficiency data indicates that MiniCPM5-2B scores 15 on the index while spending 19k output tokens per task, compared to Ling 3.0 Tiny, which scores 16 while spending 56k tokens. Granite 4.2 3B spends the same 19k tokens as MiniCPM5-2B but scores 11.

![figure](https://uploads.sitepoint.com/wp-content/uploads/large_minicpm5_2b_benchmark_analysis_e3ba57ccd9.webp)

![figure](https://uploads.sitepoint.com/wp-content/uploads/Mini_CPM_5_2_B_Ranks_First_Among_Open_Weight_Models_Under_4_B_fba7dff4a1.png)

#MiniCPM5-2B #LLM #OpenWeight #Benchmarks

---

*Source: [minicpm5-2b-benchmark-analysis](https://www.sitepoint.com/minicpm5-2b-benchmark-analysis/)*
