---
title: "TRDG Adds Non‑Latin Text Support for Synthetic OCR Data"
slug: "trdg-adds-nonlatin-text-support-for-synthetic-ocr-data"
description: "A new update to the Text Recognition Data Generator (TRDG) introduces synthetic data generation for non‑Latin scripts, expanding its utility for OCR training."
date: 2026-11-27T22:09:22+05:30
tags: [SyntheticData, OCR, TRDG, TextRecognition]
categories: ["AI", "Computer Vision", "Data Generation", "Machine Learning", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/5399488?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# TRDG Adds Non‑Latin Text Support for Synthetic OCR Data

A new update to the Text Recognition Data Generator (TRDG) introduces synthetic data generation for non‑Latin scripts, expanding its utility for OCR training.

## 🔍 Overview
- TRDG creates text‑image samples to train OCR software.
- The latest release adds support for Simplified and Traditional Chinese as well as Japanese.
- Generated texts are available in both Chinese scripts.

## 🧩 How It Works
- Run the tool from the command line after installing the `trdg` package.
- Example commands:
  - `trdg -l cn -c 1000 -w 5` – generate 1,000 Chinese images.
  - `trdg -l ja -c 1000 -w 5` – generate 1,000 Japanese images.
- Use the `-or` flag to change text orientation and `-tc '#000000,#FFFFFF'` to set a color range.

## ⚙️ Key Details
- **Installation**: `pip install trdg` (recommended inside a virtualenv).
- **Alternative install**: Clone the repo and run `pip install -r requirements.txt` to add new languages.
- **Docker**: `docker pull belval/trdg:latest` then `docker run -v /output/path/:/app/out/ -t belval/trdg:latest trdg [args]` (output path must be absolute).
- **Customisation options**:
  - `--stroke_width` – set text stroke width.
  - `--stroke_fill` – set stroke colour (requires `stroke_width > 0`).
  - `--word_split` – split on words instead of characters.
  - `--dict` – specify a custom dictionary.
  - `--font_dir` – point to a directory of fonts.
  - `--font` – use a single font for all images.
  - `--output_mask` – output a character‑level mask per image.
  - `--character_spacing` – adjust pixel spacing between characters.
  - `--fit` and `--margins` – finer layout control.

## 🚀 Availability
- The package is available on PyPI (`pip install trdg`).
- Docker image: `belval/trdg:latest`.
- Source code can be cloned for further language extensions.

## 💡 Why It Matters
- Synthetic data reduces the need for costly manual annotation.
- Adding Chinese and Japanese expands OCR research and commercial applications into Asian markets.
- Flexible CLI arguments let users tailor datasets to specific model requirements.

## 📊 Language Support Table
| Language | Scripts Supported | Example CLI |
|----------|-------------------|-------------|
| Chinese  | Simplified, Traditional | `trdg -l cn -c 1000 -w 5` |
| Japanese | — | `trdg -l ja -c 1000 -w 5` |

#SyntheticData #OCR #TRDG #TextRecognition

---

*Source: [Belval/TextRecognitionDataGenerator](https://github.com/Belval/TextRecognitionDataGenerator)*
