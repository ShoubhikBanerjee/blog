---
title: "Property Finder uncovers label bias and improves vision AI with Amazon Bedrock"
slug: "property-finder-uncovers-label-bias-and-improves-vision-ai-with-amazon-bedrock"
description: "Property Finder’s engineering team discovered that 96.8 percent of their image‑evaluation labels were inherited directly from a single vision‑language model instead of being verified by human..."
date: 2026-10-28T18:02:11+05:30
tags: [PropertyFinder, ComputerVision, AmazonBedrock, DataQuality]
categories: ["AI", "Computer Vision", "Machine Learning", "Data Engineering", "Generative AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/26/ML-21124-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Property Finder uncovers label bias and improves vision AI with Amazon Bedrock

Property Finder’s engineering team discovered that 96.8 percent of their image‑evaluation labels were inherited directly from a single vision‑language model instead of being verified by human experts. By building an unbiased ground‑truth set and applying evolutionary prompt optimization on Amazon Bedrock, they achieved higher accuracy while cutting costs by 86 percent.

## 🔍 Overview
- Co‑authored with Khaled Thabit, Meriem Boughrara, and Mohamed Desouky from Property Finder.
- The issue was uncovered while migrating the vision AI workload to a more cost‑effective option on Amazon Bedrock.
- Property Finder processes **tens of thousands of property images each day** across the MENA region, with **thousands of new listings averaging 15 images** that must be quality‑checked before going live.

## 🏗️ Evaluation Bias Discovery
- **96.8 %** of the existing evaluation labels came from the predictions of a single VLM, never independently verified.
- This left any alternative model **structurally disadvantaged** before any image was processed.
- Specific problems identified:
  - Watermark text extraction showed character‑level mistakes marked as correct, including hallucinated brand names and missing characters.
  - Photo classification forced a single label onto images that contained **multiple room types**.
  - In the remaining **3.2 %** of human‑labeled samples, annotators introduced categories outside the original specification (e.g., “Office” where no such label existed in the prompt).

## 🛠️ Building Unbiased Ground Truth
- The team hand‑annotated **356 UAE images** and a separate set of Egypt images, selected from unlabeled production listings across representative industry segments.
- The first **256 UAE images** formed the **development set** for prompt tuning.
- An **evaluation set** uses all **356 images plus 100 newly annotated images** to compare the final model.
- A **strategy and analytics expert** annotated all images; the AWS Generative AI Innovation Center team performed systematic quality reviews to resolve ambiguous cases and keep labeling consistent.
- A set of **356 images** is considered roughly sufficient to detect moderate differences between models.

## 🤖 Prompt Optimization on Amazon Bedrock
- Property Finder processed each image with Amazon Bedrock, which returns predicted attributes in **JSON** format.
- During optimization, predictions were scored with **Micro F1** against the 256‑image expert‑annotated development set.
- The optimization loop ran from **v0 to v27**:
  - Early versions used AI assistants to refine prompts.
  - Later versions employed automated optimization.
- Switching from **single‑label to multi‑label classification** removed a major source of artificial ambiguity and allowed measurement of correct secondary predictions.

## 📊 Results
- The selected model on Amazon Bedrock delivered **higher accuracy** while reducing inference cost by **86 percent** compared with the legacy approach.
- The unbiased ground‑truth data eliminated the structural disadvantage previously faced by alternative models.

## 💡 Why it Matters
- Property Finder evaluates **11 quality attributes per image**, covering:
  - Watermark detection
  - Room classification
  - Furnishing status
  - Photo quality
  - Construction indicators
- Reliable quality assessment is essential for **tens of thousands of daily listings** before they appear to users.
- A **hybrid approach**—combining models from different families, surfacing candidate labels and disagreements, and having human experts adjudicate—ensures no model output is used directly as a label.

### Attribute Coverage (sample)
| Attribute Category | Example |
|-------------------|---------|
| Watermark detection | Detects embedded branding or text watermarks |
| Room classification | Identifies living room, kitchen, bedroom, etc. |
| Furnishing status | Determines whether a room is furnished |
| Photo quality | Assesses resolution, lighting, and composition |
| Construction indicators | Flags signs of construction or renovation |



![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/26/ML-21124-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/26/ML-21124-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/26/ML-21124-3.jpg)

#PropertyFinder #ComputerVision #AmazonBedrock #DataQuality

---

*Source: [Fix evaluation bias to unlock better models on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/fix-evaluation-bias-to-unlock-better-models-on-amazon-bedrock/)*
