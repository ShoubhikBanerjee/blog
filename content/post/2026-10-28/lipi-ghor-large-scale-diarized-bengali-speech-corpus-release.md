---
title: "Lipi-Ghor: Large-Scale Diarized Bengali Speech Corpus Released"
slug: "lipi-ghor-large-scale-diarized-bengali-speech-corpus-released"
description: "A new open Bengali speech resource, Lipi‑Ghor, has been introduced. It provides 885 hours of speaker‑diarized, long‑form audio drawn from YouTube and includes a reproducible pipeline for building..."
date: 2026-10-28T12:05:05+05:30
tags: [Bengali, SpeechCorpus, ASR]
categories: ["AI", "Speech Recognition", "Natural Language Processing", "Datasets", "Computational Linguistics"]
author: "Shoubhik Banerjee"
draft: false
---

# Lipi-Ghor: Large-Scale Diarized Bengali Speech Corpus Released

A new open Bengali speech resource, Lipi‑Ghor, has been introduced. It provides 885 hours of speaker‑diarized, long‑form audio drawn from YouTube and includes a reproducible pipeline for building similar corpora in other languages.

## 📖 Overview
- Bengali is spoken by over 230 million people but is under‑resourced for spoken‑language research.
- Existing open Bengali ASR corpora are limited to short, read or crowd‑sourced speech and lack speaker diarization and long‑form audio.
- Lipi‑Ghor is the first Bengali corpus that combines large‑scale coverage with diarized, long‑form annotations.

## 📊 Corpus Details
| Attribute | Value |
|---|---|
| Audio hours | 885 |
| Source videos | 998 YouTube videos |
| Unique channels | 596 |
| Domains covered | 17 (audiobooks, drama, religious sermons, news, regional dialects, etc.) |
| Annotation format | SSTT (Speaker, Speech, Transcription, Timestamp) |
| Diarization method | Automated diarization + YouTube caption tracks |

## ⚙️ Construction Pipeline
- Uses targeted channel curation across a handful of rich domains to achieve scale.
- Combines automated speaker diarization with publicly available Bengali YouTube caption tracks.
- Designed as a replicable pipeline for any language that has sufficient captioned YouTube presence.

## 🚀 Benchmark & Evaluation
- Four widely‑used ASR models were evaluated under zero‑shot and fine‑tuned conditions.
- All four models degrade consistently on emotive, dialectal, and long‑form content.
- A human‑annotated gold evaluation split was created:
  - 17 volunteer annotators
  - 30 hours of human‑in‑the‑loop correction
  - Stratified across all 17 domains

## 📦 Availability
- Original contributions (video‑ID lists, diarization output, pipeline code, and gold annotations) are released under CC‑BY‑4.0.
- Caption‑derived transcripts are provided for research use only; raw audio is not redistributed.

## 💡 Why It Matters
- Provides a much larger and more realistic speech resource for Bengali ASR development.
- Enables research on speaker diarization, long‑form ASR, and domain variability.
- Offers a template for building comparable resources for other low‑resource languages.


#Bengali #SpeechCorpus #ASR

---

*Source: [Lipi-Ghor: A Large-Scale, Diarized, Multi-Domain Bengali Speech Corpus and a Scalable Pipeline for Building It](https://arxiv.org/abs/2610.36184v1)*
*Source: [ETC-Bench: A Multilingual Benchmark for Evaluation-Side Transcript Canonicalization](https://arxiv.org/abs/2610.36527v1)*
*Source: [Agentic Data Sampling Framework for Multilingual ASR via Linguistic-Aware Error-Driven Optimization](https://arxiv.org/abs/2610.36538v1)*
