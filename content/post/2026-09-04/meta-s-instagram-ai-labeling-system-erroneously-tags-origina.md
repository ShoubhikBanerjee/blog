---
title: "Meta's Instagram AI Labeling System Erroneously Tags Original and Minorly Edited Photos"
description: "Instagram's system for labeling synthetically generated content has recently gone haywire. Over the last few weeks, users have reported that Meta is automatically applying an 'AI Content' label to..."
date: 2026-09-04T22:05:53+05:30
tags: [Instagram, Meta, AILabeling, GenerativeAI]
categories: [AI]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/04/268439_ai_art_label_CVirginia.jpg?quality=90&strip=all&crop=0%2C10.732984293194%2C100%2C78.534031413613&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Meta's Instagram AI Labeling System Erroneously Tags Original and Minorly Edited Photos

Instagram's system for labeling synthetically generated content has recently gone haywire. Over the last few weeks, users have reported that Meta is automatically applying an "AI Content" label to original photos that were not created or edited with generative AI, while failing to tag actual AI images that should be labeled.

## 🔍 Overview

Users are reporting widespread issues with Instagram's automatic labeling system. The visible AI labels, which are intended to help people quickly identify synthetic content at a glance, are instead being placed on original photography. This includes images with minor touch-ups, such as negligible blemish-fixing or edits made with basic design tools.

## ⚙️ Key Details

Several specific issues and edge cases have emerged regarding the erroneous tags:

* **Canva Integration:** Content strategist Jess Bruno flagged concerns regarding Canva's Background Remover tool. Canva explained that some of its assistive AI tools "were being tagged as generative." While Canva claims the issue is now resolved on its end, some Threads users report that using the tool still results in their images being tagged. Conversely, other users report that none of their images edited prior to the fix were tagged, and the tool did not apply the C2PA metadata that Meta uses for detection.
* **Poisoned Content:** One user discovered that Meta applied the AI tag to an image that had been "poisoned"—subtly tweaked to make it useless for AI training or to degrade AI models—while leaving an unpoisoned version of the same content untagged.
* **Brand Accounts:** The cosmetics company About Face, founded by the singer Halsey, had the "AI Content" tag automatically applied to its recent Instagram photos. The brand's social manager clarified to commenters that no AI was used to create the images.
* **Metadata Misalignment:** Certain Apple Intelligence tools in iOS 27 (Spatial Reframing, Extend, and Clean Up) embed Google's invisible SynthID watermark. Although tagged images in these recent mishaps do not have SynthID embedded, the Meta label claims it detected signals that typically identify content as "entirely AI-generated" rather than merely modified.

## 🧩 How it works

In February, Meta announced it would scan images for IPTC and C2PA metadata to determine with reasonable certainty whether generative AI was used to create or edit them. 

In 2024, this detection system swept up pictures whose Adobe metadata indicated minor generative AI retouching, even if the final photograph was substantively unchanged. While Meta promised to tweak its approach to better reflect the amount of AI used, the latest erroneous labels do not have a clear link to generative AI usage. Outside of these mishaps, testing indicates that the label was only applied on images edited or fully generated using the Meta AI app.

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/Instagram-AI-Content-label-info.jpg?quality=90&strip=all&crop=0%2C0%2C100%2C100&w=2400)

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/Instagram-AI-label-tests.jpg?quality=90&strip=all&crop=0%2C0%2C100%2C100&w=2400)

#Instagram #Meta #AILabeling #GenerativeAI

---

*Source: [Instagram’s AI detection is a mess (again)](https://www.theverge.com/ai-artificial-intelligence/989617/instagram-ai-content-label-confusion)*
