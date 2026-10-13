---
title: "Anthropic Cuts Distillation Attacks by Up to 99% with New Anti‑Distillation Defenses"
slug: "anthropic-cuts-distillation-attacks-by-up-to-99-with-new-antidistillation-defenses"
description: "Anthropic announced that its new anti‑distillation defenses have lowered the amount of reasoning tokens that can be harvested from its Claude models by a factor of 10 to 100, while also reducing the..."
date: 2026-10-13T12:06:26+05:30
tags: [Anthropic, AISafety, Distillation, MachineLearning]
categories: ["AI", "Artificial Intelligence", "AI Safety", "Machine Learning", "Security"]
image: "https://news.lavx.hu/api/media/file/anthropic-cuts-distillation-attacks-by-up-to-99-with-new-defenses-1_1791866669420-1200x630.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic Cuts Distillation Attacks by Up to 99% with New Anti‑Distillation Defenses

Anthropic announced that its new anti‑distillation defenses have lowered the amount of reasoning tokens that can be harvested from its Claude models by a factor of 10 to 100, while also reducing the overall effectiveness of distillation attacks by 90‑99%.

## 🔍 Overview
- New measures reduce reasoning‑token extraction by **10‑100×**.
- Effectiveness of distillation attacks on Claude models lowered by **90‑99%**.
- The company notes there are **trade‑offs for legitimate users**.

## 🧩 How Distillation Attacks Work
- Distillation attacks operate at **industrial scale**.
- Attackers build **networks of fraudulent accounts** to harvest millions of model responses, especially **reasoning transcripts** that reveal how a model reaches its answers.
- Harvested data is used to train **smaller models** that mimic the larger model at a fraction of development cost.
- Example: **Zhipu's GLM‑5.3** distilled cyber capabilities from leading U.S. models, including Claude, and was judged the **most cyber‑capable open‑weights model** released to date.
- Anthropic found its safeguards previously **easily bypassed**, with models able to develop security exploits end‑to‑end.
- A reported case involved **Moonshot's Kimi** requests being secretly forwarded to Claude for distillation, including a request from a user believed to be linked to **China's People's Liberation Army** analyzing CCTV footage.

## ⚙️ New Anti‑Distillation Measures
- **Preserved thinking** introduced with **Claude Fable 5.1** and **Claude Opus 5.5** prevents new API accounts from editing Claude's prior context, blocking proxy networks from repeatedly extracting protected reasoning.
- The measure also stops weaker earlier models from reading the reasoning and limits transcript access to the **originating organization**.
- A classifier running on **Claude Sonnet 5.5, Claude Opus 5 & 5.5, Claude Fable 5 & 5.1** provides robustness comparable to bioweapon‑prevention safeguards, with a **false‑positive rate below 0.1%**.
- Persistent distillation attempts trigger **account bans**, typically within **two hours** of campaign initiation.
- Since **September 24**, Anthropic has **resumed charging** for requests blocked by safeguards in the sub‑0.1% false‑positive regime.
- The company has **banned tens of thousands of accounts** linked to distillation.
- **Developers** needed to **update integrations** to accommodate preserved thinking.
- The classifier misidentifies benign requests in **fewer than 0.1%** of cases.
- Users now pay for blocked requests in protected categories.

| Model | Role |
|-------|------|
| Claude Sonnet 5.5 | Runs anti‑distillation classifier |
| Claude Opus 5 | Runs anti‑distillation classifier |
| Claude Opus 5.5 | Runs anti‑distillation classifier |
| Claude Fable 5 | Runs anti‑distillation classifier |
| Claude Fable 5.1 | Runs anti‑distillation classifier |

## 📉 Impact
- After full implementation, **reasoning tokens extracted** by distillers fell by a factor of **10‑100**; on some days the volume was too low to measure.
- Anthropic states it has **turned away meaningful revenue and trillions of tokens** of paying traffic from distillers.
- The defenses achieve a **false‑positive rate below 0.1%**, matching the robustness of the strongest existing safeguards.

## 🚀 Outlook
- Anthropic writes: *"We expect that distillation will remain a cat‑and‑mouse game."*
- The company adds: *"We'll need to continue iterating on our defenses over time."*
- Platforms can further **slow distillation** by quickly detecting abuse and **off‑boarding fraudulent accounts**.

---
*Related Anthropic research includes experiments suggesting small AI models may be months away from self‑replicating on commercial IoT devices, and a report on unintended model actions observed during evaluations.*

![figure](https://news.lavx.hu/api/media/file/anthropic-cuts-distillation-attacks-by-up-to-99-with-new-defenses-1_1791866669420.jpg)

![figure](https://news.lavx.hu/api/media/file/anthropic-cuts-distillation-attacks-by-up-to-99-with-new-defenses-2_1791866677979.jpg)

![figure](https://news.lavx.hu/api/media/file/anthropic-cuts-distillation-attacks-by-up-to-99-with-new-defenses-3_1791866684670.jpg)

#Anthropic #AISafety #Distillation #MachineLearning

---

*Source: [Anthropic cuts distillation attacks by up to 99% with new defenses](https://news.lavx.hu/article/anthropic-cuts-distillation-attacks-by-up-to-99-with-new-defenses)*
