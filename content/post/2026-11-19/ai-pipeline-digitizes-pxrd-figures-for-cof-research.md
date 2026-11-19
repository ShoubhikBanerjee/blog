---
title: "AI pipeline digitizes PXRD figures for COF research"
slug: "ai-pipeline-digitizes-pxrd-figures-for-cof-research"
description: "A new pipeline combines vision LLMs and classical CV to digitize powder X-ray diffraction figures from COF articles, enabling reusable experimental data."
date: 2026-11-19T18:06:46+05:30
tags: [AI, ComputerVision, MaterialsScience, COFs, PXRD]
categories: ["AI", "Artificial Intelligence", "Computer Vision", "Materials Science"]
author: "Shoubhik Banerjee"
draft: false
---

# AI pipeline digitizes PXRD figures for COF research

A new pipeline combines vision LLMs and classical CV to digitize powder X-ray diffraction figures from COF articles, enabling reusable experimental data.

## 🔍 Overview
- Powder X-ray diffraction (PXRD) is the primary structural evidence for covalent organic frameworks (COFs) and many other materials.
- Yet decades of measured patterns exist only as images in published figures.

## 🧩 How it works
- The pipeline uses a vision LLM to interpret the layout of each figure, locating the diffraction plot and its curves.
- Classical computer vision (CV) then refines every trace to pixel-level accuracy.

## ⚙️ Key details
- Applied to 3,954 COF articles, the pipeline produces 11,445 calibrated diffraction curves.
- Compared with a hand digitization of 60 panels, extracted peak positions differ by a median of only 0.07 degrees.
- The digitized curves enable tracking how peak prominence, a possible marker of crystallinity, changes with synthesis conditions.

## 🚀 Availability
- The digitized curves are released in the open database COF-PEAK.

## 💡 Why it matters
- Vision LLMs and classical CV can turn such figures into reusable experimental data.
- This work presents a solution to the challenge of automatic recovery of PXRD figures, which vary widely in format.



#AI #ComputerVision #MaterialsScience #COFs #PXRD

---

*Source: [Structured Extraction of Diffraction Data from Covalent Organic Frameworks](https://arxiv.org/abs/2611.23680v1)*
