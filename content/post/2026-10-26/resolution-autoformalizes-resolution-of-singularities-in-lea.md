---
title: "Resolution autoformalizes resolution of singularities in Lean"
slug: "resolution-autoformalizes-resolution-of-singularities-in-lean"
description: "Resolution, an AI safety startup (formerly known as Sequent), has published work showing it automatically formalized a mathematical statement from statistical learning theory – the resolution of..."
date: 2026-10-26T22:04:31+05:30
tags: [AI, Autoformalization, Lean, Mathematics]
categories: ["AI", "Machine Learning", "AI Safety", "Formal Methods", "Mathematics"]
image: "https://substackcdn.com/image/fetch/$s_!3yYS!,w_1200,h_675,c_fill,f_jpg,q_auto:good,fl_progressive:steep,g_auto/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd6d17996-2bef-40a4-abe3-be72a0e8a227_258x258.png"
author: "Shoubhik Banerjee"
draft: false
---

# Resolution autoformalizes resolution of singularities in Lean

Resolution, an AI safety startup (formerly known as Sequent), has published work showing it automatically formalized a mathematical statement from statistical learning theory – the resolution of singularities.

## 🔍 Overview
- The autoformalization targets the “resolution of singularities,” which the team says “lays the groundwork for further automated research into the relationship between loss landscape geometry and generalization.”
- The effort is part of a broader push to use formal methods for advancing singular learning theory.

## 🧩 How it works
- A researcher first crafted **two plans**:
  - A high‑level, human‑interpretable version.
  - A detailed, 112‑page plan broken into atomic steps that mirror the existing literature.
- An **orchestrator agent** was then deputized to execute the plan, spawning agents that:
  - Performed pen‑and‑paper style mathematics.
  - Produced Lean code.
  - Handled support functions such as progress checks.
- The execution required little scaffolding beyond the initial plan and a set of agent skills distilled from earlier internal autoformalization work.

## ⚙️ Key details
- **Duration:** about one week.
- **Compute cost:** ~100 B input tokens (90 % cache reads) and ~300 M output tokens, estimated at **$135,000** in token spend.
- **Output:** roughly **600 k lines of Lean** code.

| Plan type | Description |
|-----------|-------------|
| High‑level | Human‑interpretable version |
| Detailed | 112‑page plan divided into atomic steps following the literature |

## 📈 Early results
- The newly built library has already been used to **extend parts of singular learning theory**.
- Formalizing the resolution of singularities enables more automation of the theory, helping to understand sampling and, in turn, to shape how models learn – a process the team calls **patterning**.

## 🚀 Outlook
- Resolution expects that the **industrialization of mathematics** will enable a “new, rigorous science of research automation.”
- The team views this autoformalization as an early step toward broader automated exploration of loss‑landscape geometry and generalization.


![figure](https://substackcdn.com/image/fetch/$s_!X6SM!,e_trim:10:white/e_trim:10:transparent/h_72,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9b933b21-aef3-4abf-8aa2-c6b2b6dcd17e_1316x448.png)

![figure](https://substackcdn.com/image/fetch/$s_!DhGS!,w_32,h_32,c_fill,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd45db1ff-96e7-4e13-a543-7eb74e4e8ae6_456x456.png)

![figure](https://substackcdn.com/image/fetch/$s_!w-KN!,w_32,h_32,c_fill,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff4dbf60d-73df-4f45-b08d-68e0a8fdd775_1024x1024.png)

#AI #Autoformalization #Lean #Mathematics

---

*Source: [Import AI 478: Math for alignment; ProgramBench; and Mirendil shows what RSI means](https://importai.substack.com/p/import-ai-478-math-for-alignment)*
