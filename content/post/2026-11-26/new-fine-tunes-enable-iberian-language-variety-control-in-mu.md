---
title: "New Fine-Tunes Enable Iberian Language Variety Control in Multilingual Translation"
slug: "new-fine-tunes-enable-iberian-language-variety-control-in-multilingual-translation"
description: "Researchers have introduced new fine-tuned variants of the MADLAD-400-3B-MT multilingual translation model that add control over regional language varieties, particularly for Spanish dialects and..."
date: 2026-11-26T18:08:23+05:30
tags: [machinetranslation, multilingualAI, languagevarieties, opensource]
categories: ["AI", "Machine Translation", "Natural Language Processing", "Multilingual AI", "Open Source Software"]
author: "Shoubhik Banerjee"
draft: false
---

# New Fine-Tunes Enable Iberian Language Variety Control in Multilingual Translation

Researchers have introduced new fine-tuned variants of the MADLAD-400-3B-MT multilingual translation model that add control over regional language varieties, particularly for Spanish dialects and minoritized languages of the Iberian Peninsula. The work addresses a key limitation where existing massively multilingual models typically provide only one tag per language with poor coverage of regional varieties and smaller languages.

## 🧩 How it works
The team created three fine-tuned versions of the base model using low-rank adaptation (LoRA), back-translation of monolingual text, and replay of the base model's own translations:

- Each variant introduces new target tags to control language varieties
- For Spanish varieties: `<2es_ES>` for Spanish as written in Spain and `<2es_419>` for Latin American Spanish
- One unified model handles three Romance languages: Asturian (`<2ast>`), Aragonese (`<2an>`), and Aranese (`<2oc_aranes>`)

## ⚙️ Key details
The Spanish variety models required careful data curation:

- Annotated 250.9 million documents from MADLAD-400's Spanish split with a Spain vs. Latin America classifier
- Applied selection rules that excluded Latin American documents from a 340-document reference set

Performance results show significant improvements:

| Model | Vocabulary Matching | Vosotros Usage | chrF++ Improvement |
|-------|---------------------|----------------|-------------------|
| Castilian (base) | 62% | 10% | - |
| Castilian (fine-tuned) | 97% | 70% | Improved |

The researchers discovered a phenomenon called "tag collapse" where new tags initialized from parent language tags drift toward the new variety (84-87% identical outputs). The Iberian model used contrastive pairs and separate learning rates for tag embeddings to maintain tag distinctiveness.

For the Iberian Peninsula model:

- Trained using publicly available data, mostly TAN-IBE Wikipedia corpora
- Matches or beats TAN-IBE Marian systems in four of six Spanish directions on FLORES+
- 1.9 BLEU behind in Spanish→Aranese (attributed to written variety differences, not quality)
- Second only to SalamandraTA-7B in most directions

## ⚠️ Trade-offs
All three fine-tuned models experience a 0.6-0.7 chrF++ decrease on average across thirteen other FLORES-200 translation directions, representing a trade-off between improved regional variety handling and reduced performance in other language pairs.

## 🚀 Availability
The models, training data, and variety classifier are released under open licences for public use.

#machinetranslation #multilingualAI #languagevarieties #opensource

---

*Source: [Teaching a Multilingual Translation Model Regional Varieties: Castilian and Latin American Spanish, Asturian, Aragonese and Aranese with MADLAD-400-3B-MT](https://arxiv.org/abs/2611.33831v1)*
