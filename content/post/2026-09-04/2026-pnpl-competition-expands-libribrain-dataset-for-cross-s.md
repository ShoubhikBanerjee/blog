---
title: "2026 PNPL Competition Expands LibriBrain Dataset for Cross-Subject Speech Decoding"
description: "The 2026 PNPL competition introduced the LibriBrain100 dataset and two new tracks aimed at advancing non‑invasive speech decoding toward a practical brain‑computer interface (BCI)."
date: 2026-09-04T18:05:55+05:30
tags: [PNPL, BCI, MEG, SpeechDecoding]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# 2026 PNPL Competition Expands LibriBrain Dataset for Cross-Subject Speech Decoding

The 2026 PNPL competition introduced the LibriBrain100 dataset and two new tracks aimed at advancing non‑invasive speech decoding toward a practical brain‑computer interface (BCI).

## 🔍 Overview
- Builds on the 2025 PNPL competition’s multi‑year curriculum for non‑invasive speech decoding.
- Adds an extended dataset and a curriculum shift to word‑classification tasks.
- Targets both high‑performance within‑subject decoding and cross‑subject generalisation.

## 📚 Background
- The 2025 competition’s ambition was to launch a curriculum that progressed from speech detection to phoneme classification, laying groundwork for a practical BCI (Landau et al., 2025).
- Winning submissions achieved F1‑macro scores of **95.6%** on speech detection and **73.6%** on phoneme classification (Elvers et al., 2026).
- These results leveraged the LibriBrain dataset, the largest within‑subject MEG collection at the time with **≈ 50 hours** of data for a single subject (Özdogan et al., 2025).
- A practical BCI, however, must work for new users with only minutes of data, not hours.

## 📊 Dataset Details
- **LibriBrain100** (Mantegna et al., 2026) extends the original dataset:
  - **32 additional subjects**, each with about **40 minutes** of recordings.
  - Expanded within‑subject data to **≈ 80 hours**.
- Provides the scale needed for cross‑subject experiments while retaining deep within‑subject recordings.

## 🚀 2026 Competition Design
- Curriculum advances to **word classification**, a higher linguistic level.
- Introduces two complementary tracks:
  1. **Deep track** – focuses on within‑subject word classification at scale, seeking the best possible performance.
  2. **Broad track** – focuses on cross‑subject generalisation, gradually reducing subject‑specific fine‑tuning data from **≈ 40 min** to **≈ 20 min** to **≈ 10 min**, a clinically feasible time frame.

## 📈 Tracks and Goals
| Track | Focus | Data constraint |
|-------|-------|-----------------|
| Deep  | Within‑subject word classification at scale | No reduction; uses full data
| Broad | Cross‑subject generalisation | Fine‑tuning limited to 40 → 20 → 10 minutes per new subject |

## 💡 Why it matters
- Demonstrates that strong decoding performance can be achieved with extensive within‑subject data (2025 results).
- Moves the field toward **generalizable, low‑data BCI solutions** that could be clinically viable for individuals with profound paralysis.
- The two‑track approach balances pushing the performance ceiling (Deep) with addressing real‑world deployment constraints (Broad).

#PNPL #BCI #MEG #SpeechDecoding

---

*Source: [The 2026 PNPL Competition: Word Classification and Efficient Cross-Subject Generalisation in LibriBrain100](https://arxiv.org/abs/2609.03231v1)*
