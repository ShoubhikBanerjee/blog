---
title: "OpenRouter Removes Three AI Providers After Data‑Handling Violations"
slug: "openrouter-removes-three-ai-providers-after-datahandling-violations"
description: "OpenRouter removed three AI providers from its platform after discovering they had violated data‑handling policies and exposed sensitive data."
date: 2026-11-24T12:08:32+05:30
tags: [OpenRouter, AI, DataSecurity, ModelBroker, ZeroDataRetention]
categories: ["AI", "Machine Learning", "Security", "Artificial Intelligence"]
image: "https://www.bleepstatic.com/content/hl-images/2026/06/29/DataLeak.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# OpenRouter Removes Three AI Providers After Data‑Handling Violations

OpenRouter removed three AI providers from its platform after discovering they had violated data‑handling policies and exposed sensitive data.

## 🔍 Overview
- OpenRouter revoked Zero Data Retention (ZDR) eligibility for 125 endpoints as a precaution.
- The company notified all potentially affected customers.
- OpenRouter removed the leaking inference providers: Together AI, Phala, and Novita.
- Atlas Cloud voluntarily withdrew its models from OpenRouter pending security testing.

## 🧩 How it Works
- OpenRouter is an AI model broker that lets developers access models from different companies using a single API key.
- When an app sends a request, OpenRouter forwards it to the provider that runs the selected model and passes the answer back.

## ⚙️ Key Details
- Dragos alerted OpenRouter after sending two million test prompts containing unique tracking links or decoy credentials.
- Dragos detected activity indicating data from at least three AI providers was exposed.
- Dragos found that in some cases credentials were leaked to outsiders and used in the wild.
- Dragos said: "We observed activity indicating that data from at least three AI providers was exposed. Our seeded test prompts were used in attempts to access our controlled test systems and canary AWS accounts."
- OpenRouter said there was no breach on its own systems, pointing the leak to the provider level.
- The providers’ incidents and responses:

| Provider | Incident | Response |
|---|---|---|
| Together AI | Exposed a GitHub repository credential, allowing unauthorized download of prompt samples (June–July) involving MiniMax M3, GLM‑5.2, Kimi K2.6 | Tightening security controls; strengthening zero‑data retention; advising users to rotate secrets |
| Phala | Server processing DeepSeek V4 Flash 0731 requests compromised; credentials obtained from affected VMs (Oct 21‑22, possibly up to Nov 8) | Tightening security controls; strengthening zero‑data retention; advising users to rotate secrets |
| Novita | Routing misconfiguration forwarded MiniMax requests to MiniMax’s official API (May 28‑Nov 11) | Tightening security controls; strengthening zero‑data retention; advising users to rotate secrets |
| Atlas Cloud | Voluntarily withdrew models pending security testing after a third‑party incident | — |
- All four providers are tightening security controls, strengthening their zero‑data retention or data deletion policies, and advising potentially impacted users to rotate any secrets that may have been exposed.
- OpenRouter is adapting Dragos’ tests for ongoing use to check whether AI providers forward or leak user requests/responses to third parties.
- OpenRouter will require validation before restoring ZDR eligibility.

## 💡 Why it Matters
- The leaks exposed sensitive data and credentials to unauthorized parties, highlighting the importance of strict data‑handling policies for AI model brokers.
- OpenRouter’s response—removing the offending providers, revoking ZDR eligibility, and adopting continuous testing—illustrates how platform operators can mitigate risks when provider security is compromised.


![figure](https://www.bleepstatic.com/images/news/u/1220909/2026/November/awskey.jpg)

![figure](https://www.bleepstatic.com/c/w/AITR-Playbook.jpg)

#OpenRouter #AI #DataSecurity #ModelBroker #ZeroDataRetention

---

*Source: [OpenRouter drops AI providers over leaked prompts and secrets](https://www.bleepingcomputer.com/news/security/openrouter-drops-ai-providers-over-leaked-prompts-and-secrets/)*
