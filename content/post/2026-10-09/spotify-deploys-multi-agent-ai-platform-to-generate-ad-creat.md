---
title: "Spotify Deploys Multi‑Agent AI Platform to Generate Ad Creatives at Scale"
slug: "spotify-deploys-multiagent-ai-platform-to-generate-ad-creatives-at-scale"
description: "Spotify has moved AI from experimental prototypes into a production‑grade multi‑agent platform that creates ad scripts, selects audiences, and enforces policy guardrails directly inside Spotify Ads..."
date: 2026-10-09T22:05:01+05:30
tags: [AIProduction, AdTech, MultiAgentAI, SpotifyAds]
categories: ["AI", "Artificial Intelligence", "Advertising Technology", "Machine Learning", "Software Architecture"]
image: "https://res.infoq.com/presentations/spotify-multi-agent-ai-architecture/en/card_header_image/twitterCard-1790847111671.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Spotify Deploys Multi‑Agent AI Platform to Generate Ad Creatives at Scale

Spotify has moved AI from experimental prototypes into a production‑grade multi‑agent platform that creates ad scripts, selects audiences, and enforces policy guardrails directly inside Spotify Ads Manager.

## 🔍 Overview
- The platform powers most of the creative‑generation pipelines for Spotify Ads Manager.
- More than 70% of ads now use these AI tools, with roughly 20,000 creatives created for over 7,000 advertisers.
- All ads are real campaigns that spend real money on real audiences.

## 🛠️ How It Works
- **LLM gateway**: Built on Vertex AI and an internal GCP platform to interpret advertiser intent.
- **Multi‑agent orchestration layer**: Runs on Google ADK (Java) and receives extracted intent via a gRPC service.
- **Agents**:
  | Agent | Role |
  |---|---|
  | Ad Script Generation Agent | Generates the ad script from the advertiser’s description |
  | Ad Guardrail Agent | Checks that the ad complies with policy rules (supplemented by the kutest moderation layer) |
  | Audience Recommendation Agent | Suggests target audiences (currently in pilot) |
- **One Agent, One Package, One Owner** – each agent is packaged and owned separately.
- **Monitoring‑info YAML** provides dashboard references and PagerDuty alerts for observability.
- The shared platform supplies metrics generation, traceability, and a developer API that calls the internal Ads API.

## 📊 Impact
- **70%+** of current ads rely on AI tools.
- **≈20,000** creatives produced.
- **≈7,000** advertisers served.
- Primary creative pipelines are now AI‑driven.

## 📅 Availability & Event
- The development will be presented at the QCon AI conference, where attendees can learn how to run AI at scale.
- Early‑bird pricing is available until **May 12th**.
- **Register now** to hear senior peers discuss inference‑latency control, safe agent guardrails, and platform standardization.

## 💡 Why It Matters
- Moving AI to production adds pressure on platforms and teams, requiring robust monitoring, guardrails, and latency management.
- A unified, multi‑agent approach lets Spotify scale ad creation while maintaining policy compliance and operational visibility.


![figure](https://res.infoq.com/presentations/spotify-multi-agent-ai-architecture/en/promoimage/qcon-ai-1784899631723-1790679493399.jpg)

#AIProduction #AdTech #MultiAgentAI #SpotifyAds

---

*Source: [Multi-Agent Patterns from Spotify’s AI Powered Advertising Platform](https://www.infoq.com/presentations/spotify-multi-agent-ai-architecture/)*
