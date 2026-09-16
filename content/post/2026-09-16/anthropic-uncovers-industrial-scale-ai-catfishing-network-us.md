---
title: "Anthropic Uncovers Industrial-Scale AI Catfishing Network Using Fraudulent Dating Apps"
slug: "anthropic-uncovers-industrial-scale-ai-catfishing-network-using-fraudulent-dating-apps"
description: "Anthropic has revealed a network of approximately 28 fraudulent dating apps that use autonomous AI personas to catfish thousands of users. The company discovered the operation after identifying a..."
date: 2026-09-17T00:45:10+05:30
tags: [Anthropic, AI, Cybersecurity, Catfishing, Fraud]
categories: ["AI", "AI Safety", "Cybersecurity", "Fraud Detection"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/268744_Inside_romance_AI_scam_apps_CVirginia2.jpg?quality=90&strip=all&crop=0%2C10.732984293194%2C100%2C78.534031413613&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic Uncovers Industrial-Scale AI Catfishing Network Using Fraudulent Dating Apps

Anthropic has revealed a network of approximately 28 fraudulent dating apps that use autonomous AI personas to catfish thousands of users. The company discovered the operation after identifying a prepaid account sending over 100,000 API requests per day via Claude.

## 🧩 How it works

The scam targets users, primarily men in their mid-to-late 30s, who match with profiles they believe are real women. The operation employs a hybrid of AI and human labor:

* **AI Personas:** Claude is used to run autonomous conversational personas, operating as if the exchanges are "ordinary roleplay or companion deployment."
* **Gig Workers:** Only one in four matches is a real person; these are paid gig workers hired to follow social media accounts or pass liveness checks on video. They respond to messages by selecting from three pregenerated replies.
* **Automated Systems:** Backend components fabricate visitors, likes, and pre-recorded video. The system also tracks users who begin to suspect they are talking to a bot.
* **Monetization:** The apps require users to purchase "coins" with real money to continue interacting with the personas.

## ⚙️ Key details

The network utilizes multiple AI providers to maintain the ruse:

| AI Model Role | Function |
| :--- | :--- |
| Claude | Runs autonomous conversational personas |
| Small non-Anthropic model | Generates short reply suggestions for gig workers; handles photo/voice moderation and face-attractiveness scoring |
| Image-editing model | Generates avatar imagery |

## 🔍 Overview

Several apps were identified as part of this network, often using descriptions emphasizing real connections:

* **Dora:** Described as a "respectful easy-to-use space to meet people who share your values" or a "warm, simple dating app for adults seeking real connection."
* **Romi:** Claims to help users "discover, connect, and chat with real people."
* **Doni:** Uses the tagline "start real companionship" to help users connect with nearby singles.

Security researcher Matthew “Zigula” Gore-Kormanik corroborated these findings while analyzing Dora. He reported receiving a call from a persona named "Jennifer" (a 41-year-old Sagittarius). Despite his microphone not being connected, the persona later messaged him stating, "your voice is way better than expected."

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/Claude-Docs.png?quality=90&strip=all&crop=15.625%2C0%2C84.375%2C100&w=2400)

#Anthropic #AI #Cybersecurity #Catfishing #Fraud

---

*Source: [The sexy AI-powered dating app scams are here](https://www.theverge.com/ai-artificial-intelligence/995348/ai-dating-app-scams)*
