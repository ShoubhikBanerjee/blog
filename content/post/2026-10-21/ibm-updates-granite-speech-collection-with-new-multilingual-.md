---
title: "IBM Updates Granite Speech Collection with New Multilingual and High-Speed Models"
slug: "ibm-updates-granite-speech-collection-with-new-multilingual-and-high-speed-models"
description: "IBM has announced three updates to its Granite Speech collection: a new speech-language model called granite-speech-5.0-2b, and revised versions of granite-speech-5.0-470m-turboctc and..."
date: 2026-10-21T22:03:49+05:30
tags: [IBM, Granite, SpeechRecognition, MachineLearning, OpenSource]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Speech Technology"]
image: "https://cdn-uploads.huggingface.co/production/uploads/653fb52cbfd890805461d691/M_JJyIOBOWVzHXdy7CVVG.png"
author: "Shoubhik Banerjee"
draft: false
---

# IBM Updates Granite Speech Collection with New Multilingual and High-Speed Models

IBM has announced three updates to its Granite Speech collection: a new speech-language model called granite-speech-5.0-2b, and revised versions of granite-speech-5.0-470m-turboctc and granite-speech-4.1-2b-plus. These models are designed to cover enterprise speech requirements, including high-accuracy transcription, translation, and long-form multi-speaker analysis.

## 🔍 Overview

| Model | Primary Use Case | Key Attributes |
| :--- | :--- | :--- |
| granite-speech-5.0-2b | High-accuracy work | 2B parameters, multilingual transcription and translation, keyword biasing |
| granite-speech-5.0-470m-turboctc | Raw speed or edge use | 470M parameters, 19,870 RTFx speed, native punctuation |
| granite-speech-4.1-2b-plus | Meetings and multi-speaker calls | Speaker attribution, tighter timestamps, 24% lower long-form WER |

## ⚙️ Key details

### granite-speech-5.0-2b
This model is the successor to granite-speech-4.1-2b and maintains the same parameter count. It was trained on 390,000 hours of public audio alongside synthetic data for Japanese ASR, translation, and keyword biasing.

* **Multilingual Capabilities:** Transcribes English, French, German, Spanish, Portuguese, and Japanese. Translates to and from English for those languages, plus English to Italian and Mandarin.
* **Advanced Prompting:** Supports Language ID prompting and allows users to request formatted output; capitalization F1 ranges from 89.7 to 99.5 across test sets.
* **Accuracy:** Features improved handling of noise, reverberation, and distant-microphone speech.
* **Keyword Biasing:** Supports lists of up to 2,000 terms to bias transcription toward product names and acronyms.

### granite-speech-5.0-470m-turboctc
Formerly an English-only model, this 470M-parameter encoder is now optimized for speed and multilingual use.

* **Multilingual Expansion:** Now supports English, Japanese, Spanish, German, French, Italian, and Portuguese.
* **Performance Gains:** The model is approximately 1.6x faster than its launch version, reaching 19,870 RTFx on the Open ASR Leaderboard by reusing a compiled Conformer block graph.
* **Edge Readiness:** Includes native punctuation and capitalization, and supports browser-based streaming via WebGPU.

### granite-speech-4.1-2b-plus
This is a drop-in replacement for the original 4.1-2b model, utilizing the same architecture, API, and prompt format with improved weights for long-form enterprise recordings.

* **Speaker Attribution:** The word diarization error rate (WDER) and speaker-attributed WER (cpWER) both decreased by 7%.
* **Timing Precision:** The average timestamp shift (AAS) has been cut by more than half, improving captions and search.
* **Long-Speech Performance:** WER on long-form test sets decreased by 24%, while keyword biasing errors fell 45% when using 20-term lists.

## 🚀 Availability

The models are released under the Apache 2.0 license and include support for:
* Transformers and vLLM
* llama.cpp
* mlx-audio for Apple Silicon

![figure](https://cdn-uploads.huggingface.co/production/uploads/653fb52cbfd890805461d691/87yRtLq4X2CwMZrDhv0L_.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/662836b742709fe826510597/gltB0o--PV_Jh0D3aDm8-.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/65cc2c288ebd392213e58899/XHWV2L_wZsFe3ekksCgvQ.webp)

#IBM #Granite #SpeechRecognition #MachineLearning #OpenSource

---

*Source: [Granite Speech 5.0: Transcribe, Translate, and Attribute more Accurately and Faster](https://huggingface.co/blog/ibm-granite/granite-speech-5)*
