---
title: "Anthropic transitions to new internal source control system called Antique"
slug: "anthropic-transitions-to-new-internal-source-control-system-called-antique"
description: "Anthropic has completed a migration from Git to a new internal source control system named Antique, designed to support significantly higher volumes of daily code changes."
date: 2026-10-14T06:05:57+05:30
tags: [Anthropic, SoftwareEngineering, SourceControl, Scaling, Infrastructure]
categories: ["AI", "Software Development", "Infrastructure", "Engineering"]
image: "https://static.simonwillison.net/static/2026/anthropic-merges-per-day.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic transitions to new internal source control system called Antique

Anthropic has completed a migration from Git to a new internal source control system named Antique, designed to support significantly higher volumes of daily code changes.

## ⚙️ Key details

* The migration was completed in five months by a team of seven people.
* Anthropic transitioned from a system that would have required over 600 PB of Git traffic per day to the new Antique system.
* The main branch history is almost 100 GB, and a compressed working copy is over 25 GB.

## 📈 Scale of operations

| Metric | Data |
| :--- | :--- |
| Code changes merged (May 2026) | ~2,500 per day |
| Code changes merged (September) | >30,000 per day |
| Daily code checkouts for CI | ~25 million |

## 🧩 How it works

* The system is called Scion, which is described as a reinvention of centralized source control similar to Subversion.
* The development process involves adversarial review to improve code quality.
* Skilled engineers are employed to steer Claude and prevent over-engineering in response to hypothetical concerns during the review process.

#Anthropic #SoftwareEngineering #SourceControl #Scaling #Infrastructure

---

*Source: [Redesigning source control at Anthropic](https://simonwillison.net/2026/Oct/13/redesigning-source-control-at-anthropic/)*
