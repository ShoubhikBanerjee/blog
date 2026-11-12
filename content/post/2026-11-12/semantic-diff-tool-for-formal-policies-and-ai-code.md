---
title: "Semantic Diff Tool for Formal Policies and AI Code"
slug: "semantic-diff-tool-for-formal-policies-and-ai-code"
description: "When reviewing code, you start with a diff. However, comparing two 3,000-line files by eye is difficult. Formal policies are even harder to compare because a textual diff often highlights syntactic..."
date: 2026-11-12T18:01:15+05:30
tags: [S, e, m, a, n, t, i, c, D, i, f, f, F, o, r, m, a, l, M, e, t, h, o, d, s, A, u, t, o, f, o, r, m, a, l, i, z, a, t, i, o, n, S, M, T, P, o, l, i, c, y, A, n, a, l, y, s, i, s]
categories: ["AI", "F", "o", "r", "m", "a", "l", "M", "e", "t", "h", "o", "d", "s", ",", "A", "I", "C", "o", "d", "e", "G", "e", "n", "e", "r", "a", "t", "i", "o", "n", ",", "P", "o", "l", "i", "c", "y", "A", "n", "a", "l", "y", "s", "i", "s", ",", "S", "e", "m", "a", "n", "t", "i", "c", "A", "n", "a", "l", "y", "s", "i", "s"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21875-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Semantic Diff Tool for Formal Policies and AI Code

When reviewing code, you start with a diff. However, comparing two 3,000-line files by eye is difficult. Formal policies are even harder to compare because a textual diff often highlights syntactic changes that don’t affect meaning. A new development introduces a semantic diff to solve this problem.

## 🔍 Overview

A semantic diff shows what two policies have in common and where they disagree. This approach addresses the limitations of standard text diffs, where reordering conjuncts, swapping the arguments of an equality, or using an equivalent predicate can cause much of a file to appear changed. A real change in behavior, such as an `Or` where the requirement says `and`, can get lost in that noise.

## ⚙️ How it works

The engine computes this diff using anti-unification, which finds a most specific common pattern for two expressions. This method is based on Plotkin’s 1970 paper.

*   **Engine Structure:** The engine works over an e-graph, which keeps track of expressions known to be equal.
*   **Justification:** Algebraic laws and domain rules justify those equalities, such as equating an external destination with one that isn’t internal.
*   **Equivalence:** If no differences remain, the policies are equivalent under those laws and rules.
*   **Completeness:** When the rules or the search are incomplete, a remaining difference might reflect an equivalence the engine has not found.

## 🚀 Use Cases

The primary use case is autoformalization, which translates natural language into a formal language.

*   **Target Languages:** SMT-LIB (standard input for Z3 and cvc5), Cedar, Dogwood, OpenShell, and Common Expression Language (CEL).
*   **LLM Generation:** A large language model (LLM) generates the formal artifact from prose.
*   **Comparison Process:** Run the model twice to produce two different formalizations. A semantic diff shows where they agree and where they differ.
*   **Candidate Generation:** Generate more candidates by varying the model, prompt, or sampling temperature.

## 💡 Benefits

*   **Analogy:** This is a formal-methods analogue of semantic entropy, described by Farquhar et al. in Nature (2024).
*   **Information Preservation:** For formal outputs, anti-unification preserves more information.
*   **Counterexamples:** Counterexamples help explain the consequences of a disagreement. An SMT solver can find a concrete assignment that satisfies one formula and violates the other.
*   **Review Visibility:** When several translations agree on part of a requirement, the diff shows that part once. Where they disagree, it keeps the alternatives visible for review.
*   **Operator Handling:** The reordering doesn’t appear in the result because `And` is declared associative, commutative, and idempotent.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21875-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21875-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21875-3.jpg)

#S #e #m #a #n #t #i #c #D #i #f #f #, # #F #o #r #m #a #l #M #e #t #h #o #d #s #, # #A #u #t #o #f #o #r #m #a #l #i #z #a #t #i #o #n #, # #S #M #T #, # #P #o #l #i #c #y #A #n #a #l #y #s #i #s

---

*Source: [Semantic diffing of formal policies with anti-unification | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/semantic-diffing-of-formal-policies-with-anti-unification/)*
