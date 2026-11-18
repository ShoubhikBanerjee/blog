---
title: "Python Solver Wins SOICT 2026 Integrated Transportation Contest"
slug: "python-solver-wins-soict-2026-integrated-transportation-contest"
description: "A single‑file Python solver was submitted to the second round of the SOICT 2026 contest for the Integrated Passenger and Parcel Transportation problem, a selective pickup‑and‑delivery routing problem..."
date: 2026-11-18T18:09:03+05:30
tags: [SOICT, Python, Routing, ALNS, Optimization]
categories: ["AI", "Optimization", "Routing", "Python", "Algorithm Design"]
author: "Shoubhik Banerjee"
draft: false
---

# Python Solver Wins SOICT 2026 Integrated Transportation Contest

A single‑file Python solver was submitted to the second round of the SOICT 2026 contest for the Integrated Passenger and Parcel Transportation problem, a selective pickup‑and‑delivery routing problem with time windows, open routes and heterogeneous taxis.

## 🔍 Overview
The contest task involved integrating passenger and parcel transportation under constraints of time windows, open routes, and heterogeneous taxi fleets.

## 🧩 How it Works
The solver combines:
- A constant‑time insertion test based on latest‑arrival slack.
- Greedy insertion.
- Local search.
- Adaptive Large Neighborhood Search (ALNS) with simulated‑annealing acceptance.
- An exact route‑selection engine.

| Component | Description |
|---|---|
| Constant‑time insertion test | Based on latest‑arrival slack |
| Greedy insertion | |
| Local search | |
| ALNS with simulated‑annealing acceptance | |
| Exact route‑selection engine | Enumerates, for every taxi, the best feasible route for each request set and then solves the resulting set‑packing problem by branch‑and‑bound strengthened with route‑based large neighborhood search, Lagrangian bounds and reduced‑cost fixing |

## ⚙️ Key details
- The exact engine is chosen automatically from the instance size.
- An independent verifier and a watchdog guarantee that a valid answer is always printed.
- Official evaluation: 38 scored instances, 5‑minute limit, total benefit 487,237.
- Every run finished within 277 seconds, using at most 279 MB.
- 28 of the 38 instances terminated well before the limit.


#SOICT #Python #Routing #ALNS #Optimization

---

*Source: [A Hybrid Exact-Heuristic Solver for the Integrated Passenger and Parcel Transportation Problem](https://arxiv.org/abs/2611.22043v1)*
