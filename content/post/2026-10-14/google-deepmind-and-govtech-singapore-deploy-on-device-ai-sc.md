---
title: "Google DeepMind and GovTech Singapore Deploy On‑Device AI Scam Detector"
slug: "google-deepmind-and-govtech-singapore-deploy-ondevice-ai-scam-detector"
description: "Google DeepMind and Singapore’s Government Technology Agency (GovTech) have jointly released a privacy‑preserving, on‑device scam detection model as part of the National AI Partnership."
date: 2026-10-14T18:06:09+05:30
tags: [AI, ScamDetection, Privacy, Singapore]
categories: ["AI", "Artificial Intelligence", "Cybersecurity", "Privacy Protection", "Public Policy"]
image: "https://lh3.googleusercontent.com/m134KeViYlQXqWaac-fW1TuTvCk1ZQ2EnHF72xH6anzjd4iKukfGHvV3o5PiDTJfSytjxUF2E1rwAAHlZ4ZyCkGkOHV7Uij2ZZ3zsbVZUAFCMCccZQ=w1200-h630-n-nu-rw"
author: "Shoubhik Banerjee"
draft: false
---

# Google DeepMind and GovTech Singapore Deploy On‑Device AI Scam Detector

Google DeepMind and Singapore’s Government Technology Agency (GovTech) have jointly released a privacy‑preserving, on‑device scam detection model as part of the National AI Partnership.

## 🔍 Overview
- The model is fine‑tuned on local scam conversations and runs entirely on the user’s device.
- It aims to protect citizens from complex social‑engineering scams while keeping conversation data private.

## 📈 Problem Landscape
- Scams such as investment fraud, fake job offers, and impersonation of public officials make up over half of Singapore’s reported crimes.
- These scams have caused more than S$4 billion in losses since 2019 and account for up to 80 % of all loss amounts.
- Attackers have shifted from simple phishing to elaborate social‑engineering tactics that involve convincing conversations before requesting money.

## 🤝 Collaboration
- Google DeepMind and GovTech Singapore are collaborating under the National AI Partnership with the Singapore Government.
- Development was performed inside GovTech Singapore’s managed GCP environment (a “Sovereign Sandbox”).
- Training data excluded private or personally identifiable information and used anonymised scam‑report and intelligence feeds.

## 🛡️ How the On‑Device Model Works
- **Two‑stage pipeline**:
  1. **Stage 1** – a lightweight, efficient classifier screens inbound messages with minimal power consumption.
  2. **Stage 2** – an in‑context analysis using the fine‑tuned Gemma model examines a larger snapshot of the conversation to confirm a threat or dismiss a false alarm.
- When a manipulative conversational pattern is detected, a real‑time warning appears on the device, prompting the user to pause and verify before sharing sensitive information or funds.
- The model processes conversation data only on the device, with user consent, and neither Google nor the Singapore Government can access the user’s messages.

## ⚙️ Technical Details
- The lightweight Gemma model was fine‑tuned on local scam dialogues, including impersonations of public institutions, banks, local figures, and trending regional schemes.
- Generic models often struggle with local deception techniques; the fine‑tuned model can distinguish benign social chatter from genuine manipulation.
- Stress‑testing involved synthetic dialogues and local corpora to cover diverse scam categories and evolving impersonation tactics.

## 🚀 Deployment & Availability
- The rollout will be carefully phased and developed in partnership with the Singapore Government.
- Integration into applications will allow faster analysis of conversation patterns and help citizens act before financial or credential exposure occurs.
- The collaboration was presented at Singapore International Cyber Week (SICW 2026) as a model for messaging platforms that balance user protection with end‑to‑end encryption.

## 💡 Why It Matters
- Demonstrates how AI can counter criminal activity without compromising safety or privacy.
- Provides a concrete example of local, real‑time scam detection while preserving the confidentiality of chat interactions.
- Sets a precedent for future AI‑driven security solutions that respect sovereign data governance.

#AI #ScamDetection #Privacy #Singapore

---

*Source: [On-Device AI Against Scams: Google DeepMind & MDDI](https://deepmind.google/blog/on-device-ai-scam-detection-mddi/)*
