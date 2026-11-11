---
title: "Google DeepMind Unveils AlphaGenome 2 for Cell-Specific Genetic Variant Prediction"
slug: "google-deepmind-unveils-alphagenome-2-for-cell-specific-genetic-variant-prediction"
description: "Google DeepMind has unveiled AlphaGenome 2, a new AI model designed to predict how changes in DNA affect specific human cell types and states. As the successor to the original AlphaGenome model..."
date: 2026-11-11T22:05:42+05:30
tags: [DeepMind, Genomics, AlphaGenome, Bioinformatics, AIresearch]
categories: ["AI", "Artificial Intelligence", "Genomics", "Biotechnology"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/alphagenome-atlas-cover__background.jpg?quality=90&strip=all&crop=0%2C3.4613147178592%2C100%2C93.077370564282&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Google DeepMind Unveils AlphaGenome 2 for Cell-Specific Genetic Variant Prediction

Google DeepMind has unveiled AlphaGenome 2, a new AI model designed to predict how changes in DNA affect specific human cell types and states. As the successor to the original AlphaGenome model released last year, the new version captures how the same genetic variant can have different effects depending on the cell type—such as heart muscle, skin, or immune cells—and their current activity levels.

## 🔍 Overview

AlphaGenome 2 is designed to provide a finer-grained view of the genome than its predecessor, allowing researchers to identify disease-relevant effects in specific cells that broad-tissue models might miss. The model turns static cell atlases, which catalog millions of cells, into predictive engines that can simulate how subtle DNA variations drive human traits and disease.

## 🧩 How it works

The model represents a fundamental redesign of how cell types are treated in genetic prediction. While the first version of AlphaGenome predicted properties across thousands of experiments in parallel, AlphaGenome 2 is a conditional model that predicts DNA effects for one tissue, cell type, or state at a time.

*   **Inputs:** It uses both a million-letter DNA sequence and the target biological condition as inputs at every stage of its architecture.
*   **Training Data:** It was trained on over 107 million individual cell profiles across 68 tissues, utilizing both bulk and single-cell data from human and mouse samples.
*   **Readouts:** The model predicts gene expression, histone modifications, chromatin accessibility, and DNA methylation.
*   **Generalization:** It can make predictions for new types of cells and biological states without retraining, using a single-cell RNA-seq snapshot as a cell state representation.

## ⚙️ Key details

According to Google DeepMind, AlphaGenome 2 identifies nearly twice as many variants that change gene expression in cells compared to its previous state-of-the-art model. Performance metrics from the TenK10K dataset show significant improvements in identifying causal variants and gene effects.

| Metric | AlphaGenome (Fine-tuned) | AlphaGenome 2 |
| :--- | :--- | :--- |
| Causal Variant Identification | 16% | 30% |
| Directional Gene Effects | 23% | 43% |
| DNA Readouts | Gene expression, histone, chromatin | Above + DNA methylation |

## 💡 Why it matters

Adam Gayoso, a research scientist at Google DeepMind, stated that the big breakthrough is "tying human genetics to cell biology." This specificity is vital for drug development; Žiga Avsec, DeepMind’s genomics lead, explained that "When you develop drugs, you’re targeting specific proteins and specific cell types." 

In a real-world application, AlphaGenome 2 computationally reproduced a finding related to Inflammatory Bowel Disease (IBD). It singled out a specific variant that boosts the ETS2 gene in gut macrophages while leaving other cell types largely unaffected. Longer term, these models could contribute to the creation of digital simulations known as "virtual cells."

## 🚀 Availability

Google is making AlphaGenome 2 available for non-commercial research through the AlphaGenome API starting today. A limited private preview is also available for commercial research. Although it is the successor to the original model, AlphaGenome 2 is not replacing it yet because its detailed predictions are computationally more expensive to produce than those of its predecessor.

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/alphagenome-atlas-cover__background.jpg?quality=90&strip=all&crop=7.8125%2C0%2C84.375%2C100&w=2400)

![figure](https://storage.googleapis.com/gdm-deepmind-com-prod-public/media/original_images/EUdRzfXXT2oOcMoR/ag1_vs_ag2_expr_cond_gdm_light_no_outline.gif)

#DeepMind #Genomics #AlphaGenome #Bioinformatics #AIresearch

---

*Source: [Google’s AlphaGenome 2 zooms in on the cellular roots of disease](https://www.theverge.com/ai-artificial-intelligence/1031524/google-deepmind-alphagenome-2-genetic-ai-model)*
*Source: [AlphaGenome 2: Deciphering how cells read DNA to better understand disease](https://deepmind.google/blog/alphagenome-2-deciphering-how-cells-read-dna-to-better-understand-disease/)*
