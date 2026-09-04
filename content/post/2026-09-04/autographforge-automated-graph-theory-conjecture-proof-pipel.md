---
title: "AutoGraphForge: Automated Graph Theory Conjecture–Proof Pipeline Launched"
description: "An automated system called **AutoGraphForge** has been built to generate, refute, formalize, and prove graph‑theoretic conjectures."
date: 2026-09-04T22:05:53+05:30
tags: [graphtheory, automatedreasoning, Lean4, AI]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# AutoGraphForge: Automated Graph Theory Conjecture–Proof Pipeline Launched

An automated system called **AutoGraphForge** has been built to generate, refute, formalize, and prove graph‑theoretic conjectures.

## 🔍 Overview
- AutoGraphForge is a computational pipeline that automates the entire conjecture life‑cycle for graph theory.
- It runs on a high‑performance computing (HPC) cluster and has passed initial sanity checks.

## 🧩 How it works
- **Conjecture generation** is counterexample‑guided and proceeds in rounds. A Graffiti3 generator proposes conjectures over a small, evolving snapshot table $T$ (initially a few hundred graphs with their computed invariants) that grows only by counterexamples to its own conjectures.
- A **novelty filter** contains 559 classical and folklore relations, closed under transitive composition and linear identity substitution. It decides via a linear program whether a candidate is already implied by known results.
- Surviving candidates are tested against a dataset of about 348,000 graphs, which unions the complete House of Graphs invariant export, the exhaustive census of all connected graphs on at most nine vertices, several extremal families (strongly regular, minimal Ramsey, Cayley, cages, barbells, lollipops, spiders), and random models.
- Counterexample‑search algorithms then attack the remainder.
- After several rounds on the HPC cluster, the loop yields **6,522 conjectures** that survived the refutation dataset, the novelty filter, and every active‑search run. Among these are nontrivial relations between the annihilation number and the edge‑cover number for bipartite and regular graphs, which were proved by hand.

## ⚙️ Formalization & Proving Stage
- Each surviving conjecture is deterministically translated into a Lean 4 statement skeleton.
- Every candidate proof is kernel‑verified against a pinned `mathlib4` and a custom invariant preamble.
- Two neural provers are integrated behind the independent kernel check:
  
| Model | Role |
|---|---|
| DeepSeek‑Prover‑V2‑671B (served with vLLM) | Neural prover for Lean statements |
| OProver‑32B (Lean‑specialised) | Neural prover for Lean statements |

## 🚀 Availability
- The pipeline is implemented end‑to‑end and is currently running on the cluster.
- It passes initial sanity checks and is ready for further research use.

#graphtheory #automatedreasoning #Lean4 #AI

---

*Source: [AutoGraphForge: Towards Automated Graph Theory Discovery](https://arxiv.org/abs/2609.03478v1)*
