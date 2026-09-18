---
title: "Study Introduces Structural-Complexity Index for Prompt Evaluation"
slug: "study-introduces-structural-complexity-index-for-prompt-evaluation"
description: "A new study introduces a six-dimension prompt-side structural-complexity index scored before generation. The research evaluates 105,000 generations across 21 models to analyze performance thresholds..."
date: 2026-09-18T12:08:53+05:30
tags: [P, r, o, m, p, t, E, n, g, i, n, e, e, r, i, n, g, L, L, M, E, v, a, l, u, a, t, i, o, n, S, t, r, u, c, t, u, r, a, l, C, o, m, p, l, e, x, i, t, y, P, y, t, h, o, n, R, e, l, i, a, b, i, l, i, t, y]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "N", "a", "t", "u", "r", "a", "l", "L", "a", "n", "g", "u", "a", "g", "e", "P", "r", "o", "c", "e", "s", "s", "i", "n", "g", ",", "S", "o", "f", "t", "w", "a", "r", "e", "E", "n", "g", "i", "n", "e", "e", "r", "i", "n", "g", ",", "R", "e", "s", "e", "a", "r", "c", "h"]
author: "Shoubhik Banerjee"
draft: false
---

# Study Introduces Structural-Complexity Index for Prompt Evaluation

A new study introduces a six-dimension prompt-side structural-complexity index scored before generation. The research evaluates 105,000 generations across 21 models to analyze performance thresholds and reliability regimes.

## 🔍 Overview
The contribution is a pre-generation measurement framework and a bounded observational analysis of reliability regimes. The index is scored separately from correctness.

## 🧩 Methodology
*   **Dataset:** The study selects 5,000 Python prompts across six bands of a preliminary single-rater rubric.
*   **Raters:** Four out-of-panel LLM raters rescore the locked prompts, giving 19,997 score rows.
*   **Generations:** The study evaluates 21 models per prompt, yielding 105,000 generations.
*   **Reliability:** Composite inter-rater reliability is ICC = 0.872 on the 4,998 prompts with all four ratings.

## ⚙️ Key Findings
*   **Performance Breakpoints:**
    *   Unadjusted mean-pooled analysis shows a nonmonotone breakpoint at composite 13.75.
    *   Task-type fixed effects shift the breakpoint to 10.75.
    *   A construction-frame control shifts it to 8.50.
*   **Model-Specific Fits:** The analysis includes 16 upward and five downward changes.
*   **Complexity Analysis:** Among zero-pass generations with computable Lizard complexity, 28.5% pair a prompt composite above 8 with output complexity at most 10.

## 📊 Reliability and Calibration
*   Human agreement is moderate and rater-dependent on a disagreement-enriched calibration set.
*   Paraphrase and cross-language rescoring preserve score ordering.

## 💡 Conclusion
Overidentification tests reject the joint restrictions on the six dimensions. The composite is treated as an index, and no causal interpretation is made of the 2SLS estimates.

#P #r #o #m #p #t #E #n #g #i #n #e #e #r #i #n #g #, # #L #L #M #E #v #a #l #u #a #t #i #o #n #, # #S #t #r #u #c #t #u #r #a #l #C #o #m #p #l #e #x #i #t #y #, # #P #y #t #h #o #n #, # #R #e #l #i #a #b #i #l #i #t #y

---

*Source: [The Complexity Kink: A Prompt-Side Structural Complexity Index for Code-Generation Reliability](https://arxiv.org/abs/2609.19616v1)*
