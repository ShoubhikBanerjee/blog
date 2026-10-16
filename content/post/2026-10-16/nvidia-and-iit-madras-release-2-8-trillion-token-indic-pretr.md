---
title: "NVIDIA and IIT Madras Release 2.8 Trillion‑Token Indic Pretraining Corpus"
slug: "nvidia-and-iit-madras-release-2-8-trilliontoken-indic-pretraining-corpus"
description: "NVIDIA, in collaboration with IIT Madras and its AI4Bharat lab, is releasing **Nemotron‑pretraining‑Indic‑v1**, a 2.8 trillion‑token dataset covering all 22 Indian Constitution languages, together..."
date: 2026-10-16T12:05:34+05:30
tags: [NVIDIA, IndicAI, OpenData, AI4Bharat, Pretraining]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Data Engineering", "AI Research"]
image: "https://cdn-uploads.huggingface.co/production/uploads/68d2fec8856b85d927e44d32/x0aObe_0mduBjWFuKBGoV.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA and IIT Madras Release 2.8 Trillion‑Token Indic Pretraining Corpus

NVIDIA, in collaboration with IIT Madras and its AI4Bharat lab, is releasing **Nemotron‑pretraining‑Indic‑v1**, a 2.8 trillion‑token dataset covering all 22 Indian Constitution languages, together with an open GPU‑accelerated data‑generation pipeline.

## 🔍 Overview
- Approx. 2.8 trillion tokens across **22 Indian languages** (the languages listed in India’s Constitution, spoken by 97 % of Indians – about 1.2 billion citizens at the 2011 Census).\
- Developed by **NVIDIA**, **IIT Madras**, and **AI4Bharat**.\
- Released alongside an open, GPU‑accelerated synthetic‑data pipeline that captures prompts, LLM workflows, and quality checks.\
- Extends prior resources such as AI4Bharat’s **Sangraha** open pretraining corpus.

## 🧩 How it works
- The pipeline is built with **NeMo Data Designer**, NVIDIA’s open‑source framework for generating synthetic data.\
- It follows a **four‑stage synthetic‑data workflow** (translation → quality assessment → targeted repair → final validation) implemented using **Gemma‑4‑31B‑it**.\
- Each output retains a source identifier, allowing developers to trace synthetic text back to its original document.\
- Quality checks preserve technical content such as equations, tables, and code.

## ⚙️ Key details
- **Token composition** (Gemma‑4 tokenizer):\
  - 2,601.0 billion native‑script tokens\
  - 224.6 billion romanized tokens\
- **Script coverage**: native‑script data for all 22 languages and romanized text for 12 languages, giving **34 language‑script configurations**.\
- **Languages by script**:
  | Language | Script Type |
  |----------|------------|
  | Assamese | Native |
  | Bodo | Native |
  | Dogri | Native |
  | Gujarati | Native / Romanized |
  | Hindi | Native / Romanized |
  | Kannada | Native / Romanized |
  | Malayalam | Native / Romanized |
  | Marathi | Native / Romanized |
  | Nepali | Native / Romanized |
  | Odia | Native / Romanized |
  | Punjabi | Native / Romanized |
  | Tamil | Native / Romanized |
  | Telugu | Native / Romanized |
  | Urdu | Native / Romanized |
  | Kashmiri | Native |
  | Konkani | Native |
  | Maithili | Native |
  | Manipuri | Native |
  | Sanskrit | Native |
  | Santali | Native |
  | Sindhi | Native |
- Romanized text means Indic‑language text written in Latin script, **not** an English translation.\
- The corpus was assembled from **15 Nemotron‑CC‑v2 subsets** covering web text, question‑answer material, mathematics, code, and other specialized content.

## 🚀 Availability
- Nemotron‑pretraining‑Indic‑v1 and the accompanying data‑generation pipeline will be released **soon** as open resources for model builders.

## 💡 Why it matters
- AI4Bharat’s director Mitesh Khapra identified the lack of data as the core reason Indian language technology lags behind English.\
- Providing a massive, high‑quality multilingual corpus—including technical content such as mathematics and code—gives researchers and developers a foundation to build models that can explain concepts, solve problems, and answer questions in Indian languages.


![figure](https://cdn-uploads.huggingface.co/production/uploads/68d2fec8856b85d927e44d32/VmVFMKjOsoNkEKfQ7cRnh.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/68d2fec8856b85d927e44d32/PCtm5uAGrdrp8kgHXb6y3.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/68d2fec8856b85d927e44d32/ZPR2A2wDoNW6OVb4-GX63.png)

#NVIDIA #IndicAI #OpenData #AI4Bharat #Pretraining

---

*Source: [Scaling Indic Pretraining: 2.8 Trillion Tokens and an Open Data Generation Pipeline](https://huggingface.co/blog/nvidia/scaling-indic-pretraining)*
