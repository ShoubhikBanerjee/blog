---
title: "New Counterfactual Routing Solution Ranks Fourth and Sets Speed Record at IJCAI 2025"
description: "A team submitted a solution to the IJCAI 2025 **Counterfactual Routing Competition** that focuses on generating counterfactual explanations for the shortest‑path problem."
date: 2026-09-04T18:05:55+05:30
tags: [IJCAI, CounterfactualRouting, AIOptimization, IntegerProgramming]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# New Counterfactual Routing Solution Ranks Fourth and Sets Speed Record at IJCAI 2025

A team submitted a solution to the IJCAI 2025 **Counterfactual Routing Competition** that focuses on generating counterfactual explanations for the shortest‑path problem.

## 🔍 Overview
- The competition’s goal is to identify the minimal changes to a road network that would make a user‑chosen route the optimal one.
- This enables explanations such as “Your suggested route would indeed have been optimal, if road X were not a bicycle path.”

## 🧩 How it works
- The problem is modeled as an **integer program**.
- Constraints are incorporated iteratively until an exact solution is reached.

## ⚡ Performance
- In the final evaluation on held‑out test instances, the method ranked **fourth** in solution quality.
- It obtained the fastest solution on **every** instance.
- **Average runtime:** 9.0 seconds, compared with 118.8 seconds for the next‑fastest submission.

| Metric                     | Our method | Next fastest |
|----------------------------|------------|--------------|
| Solution quality rank      | 4th        | –            |
| Average runtime (seconds) | 9.0        | 118.8        |


#IJCAI #CounterfactualRouting #AIOptimization #IntegerProgramming

---

*Source: [Counterfactual Routing Using Integer Programming with Constraint Generation](https://arxiv.org/abs/2609.03707v1)*
