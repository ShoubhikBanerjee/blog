---
title: "Open‑Weight Model Generates Design‑Language‑Consistent Slide Decks"
slug: "openweight-model-generates-designlanguageconsistent-slide-decks"
description: "Ask a frontier model for a slide deck and you'll get a good one. Ask for ten and they start to look alike: the same tasteful defaults, the same house style, a faint “AI‑generated deck” look. Frontier..."
date: 2026-11-04T12:02:19+05:30
tags: [OpenSource, PresentationAI, FineTuning, DesignSystems]
categories: ["AI", "Machine Learning", "Generative AI", "Productivity Tools"]
image: "https://cdn-uploads.huggingface.co/production/uploads/63890e3843d8b0797a0ad606/5pHD09UHuAK-6OyKGKimD.png"
author: "Shoubhik Banerjee"
draft: false
---

# Open‑Weight Model Generates Design‑Language‑Consistent Slide Decks

Ask a frontier model for a slide deck and you'll get a good one. Ask for ten and they start to look alike: the same tasteful defaults, the same house style, a faint “AI‑generated deck” look. Frontier models have their own house style, and no amount of prompting stops them drifting back to it. Both of those point to a model you own: open weights, running on your own infrastructure, trained on your own design language.

## 🔍 Overview
- Small open‑weight models that you can self‑host are normally bad at deck generation.
- Their decks often have broken elements: titles that vanish, text running off the slide, and stacked shapes.
- The **Palette** hypothesis is that a small open‑weight model, trained on synthetic data in your design language and checked by a harness, can compete with frontier systems while you keep ownership of the result.

## 🧩 How it works
- **Story planning** – you decide the number of slides, the content of each, and which visual (chart or table) each slide gets.
- **Designer** reads the plan and writes a structured JSON brief containing the palette, type system, and for each slide: layout, exact content, and a short design rationale.
- **Coder** takes a slide’s spec from the brief and writes `pptxgenjs` JavaScript that draws the slide, preceded by its reasoning.
- Because every slide’s context is fixed before any code is written, the coder runs each slide in parallel, making the coding stage about 6–7× faster.
- A harness renders each generated deck, checks for overlaps and overflow, repairs broken slides, and rewrites the reasoning as a counter‑factual explanation of the fix.

## ⚙️ Training & Data
- A 20B model was fine‑tuned to build decks the way people do: a designer plans the deck and a coder draws each slide.
- Training data follows the **IBM Design Language**.
- The adapter was trained with **LoRA** instead of full fine‑tuning, allowing cheap experiments while preserving the base model’s knowledge.
- Coder examples are ~5× longer than designer examples; to avoid under‑training the designer, its examples were oversampled 5×.
- Each deck starts from a recipe that sets genre, length, layouts, and any user directives, controlling the data coverage.
- Around **1,000 decks** were generated, covering roughly **10,000 slides**.

## 📊 Performance
- On **PresentBench**, the model ranks first on two of the three measured domains.
- Small models often mis‑calculate layout arithmetic (e.g., whether a 75‑character title fits on two lines at 56pt), leading to overlapping shapes or overflow.
- Example design rationale: 
  > "Revenue for four quarters, with one clear upward trend. I considered a table, but the point of this slide is the trend, not the exact figures, so a bar chart makes it visible at a glance."
- Example title sizing decision:
  > "The title is 62 characters. At 44pt it would wrap to three lines and run into the chart below, so I set it at 36pt, which fits on two lines and leaves room above the chart."

## 🚧 Limitations
- The worst failure mode is a slide that contains facts not present in the input; a prompt rule could not prevent this hallucination.
- Overlaps and overflow still occur occasionally; they are detected by the harness and repaired post‑generation.

## 💡 Why it matters
- Ownership: the model runs on your own infrastructure with open weights, preserving control over proprietary design language.
- Consistency: decks follow a specific design system rather than the generic house style of frontier models.
- Cost: fine‑tuning a 20B model with LoRA and synthetic data is cheaper than accessing large proprietary APIs.
- Speed: parallel slide coding accelerates the generation pipeline 6–7×.


![figure](https://cdn-uploads.huggingface.co/production/uploads/63890e3843d8b0797a0ad606/YTsME8ZIwzzxmo-QmpTQq.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/63890e3843d8b0797a0ad606/PZoiyAFg_nrWRryQhjGN_.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/63890e3843d8b0797a0ad606/iZzBRJXOUxncecFIEgw-B.png)

#OpenSource #PresentationAI #FineTuning #DesignSystems

---

*Source: [Palette: teaching a small model to build decks in your design language](https://huggingface.co/blog/ibm-research/palette-deck-building)*
