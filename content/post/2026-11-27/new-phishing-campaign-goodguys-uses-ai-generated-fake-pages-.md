---
title: "New phishing campaign 'GoodGuys' uses AI-generated fake pages to steal corporate credentials"
slug: "new-phishing-campaign-goodguys-uses-ai-generated-fake-pages-to-steal-corporate-credentials"
description: "An ongoing phishing campaign dubbed 'GoodGuys' impersonates major brands including Google, Nvidia, Accenture, and SpaceX to steal corporate Google and Okta credentials using fake paid interview and..."
date: 2026-11-27T22:09:22+05:30
tags: []
categories: ["AI"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/06/Phishing.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# New phishing campaign 'GoodGuys' uses AI-generated fake pages to steal corporate credentials

An ongoing phishing campaign dubbed 'GoodGuys' impersonates major brands including Google, Nvidia, Accenture, and SpaceX to steal corporate Google and Okta credentials using fake paid interview and webinar invitations.

The campaign was discovered by cybersecurity firm Push Security, which has tracked it since October 13. It impersonates eight companies: Accenture, American Express, Coca-Cola, Culver's, Google Cloud, Nvidia, SpaceX, and Spotify.

## 🧩 How it works

The threat actors abuse legitimate email and event platforms, including HireVue, SendGrid, Mandrill, and Cvent, to distribute phishing links. In one attack, a phishing email sent through HireVue invited recipients to attend a Google Cloud webinar about deploying AI applications into production.

The phishing links typically lead to a CAPTCHA challenge before displaying a website impersonating the company that supposedly sent the invitation. Each website features customized branding and lures, with the Nvidia phishing site offering $500 to participate in an AI feedback study and the Accenture site offering $600 for an expert interview.

The sites ultimately prompt visitors to sign in with their Google accounts to validate their invitations, allowing the attackers to steal their credentials. The phishing kit specifically targets corporate accounts and rejects email addresses associated with Gmail, Yahoo, and Outlook.

Unlike adversary-in-the-middle (AiTM) phishing kits that use reverse proxies, GoodGuys uses fake authentication forms controlled by an attacker-controlled server. After victims enter their Google credentials, the phishing page can display various multifactor authentication (MFA) challenges, including SMS codes, authenticator codes, and Google sign-in prompts requiring users to select a matching number on their phones.

The kit also includes fake Okta authentication forms and support for Okta Verify push notifications. Push Security believes the threat actors manually attempt to log in using the stolen credentials, instructing the phishing page to display whatever MFA or security challenges Google or Okta show during authentication.

## ⚙️ Key details

The threat actors use domains themed around interviews, webinars, and research studies, creating brand-specific subdomains to host the phishing pages, such as:

| Domain | Target | Incentive |
|--------|--------|----------|
| accenture.international-interviews.com | Accenture | $600 for expert interview |
| nvidia.feedback-study.com | Nvidia | $500 for AI feedback study |
| google.webinar-cloud.com | Google Cloud | Webinar access |
| spotify.interview-experts.com | Spotify | Expert interview |

The phishing kit may have been developed using an AI coding assistant. Hidden accessibility labels found in every analyzed version of the kit include 'Sign-in simulation' and 'GoodGuys sign-in simulation.' These labels are in accessibility text that only screen readers announce.

"The sign-in card in every build carries two hidden labels: 'Sign-in simulation' and 'GoodGuys sign-in simulation,'" explained Push Security. "Calling the page a sign-in 'simulation' for a made-up company is the kind of framing someone would use to get an AI coding assistant past its guardrails when asking it to build a phishing page."

Researchers also discovered a potentially related phishing campaign using fake Coca-Cola interview invitations and the Evilginx phishing kit to target Google Ads accounts. While both campaigns used the same abused SendGrid click tracker and identical Coca-Cola branding assets, differences in code and infrastructure prevented researchers from conclusively linking the attacks to the same threat actor.

## 🚀 Availability

The campaign has been active since at least October 13, when Push Security first detected it. The attackers continue to use the same methodology across multiple platforms and brand impersonations.

## 💡 Why it matters

This campaign demonstrates how attackers are leveraging AI-assisted development to create sophisticated phishing infrastructure at scale, targeting corporate credentials through legitimate-looking platforms and monetary incentives.

---

*Source: [Fake paid expert interviews impersonate brands to steal Google logins](https://www.bleepingcomputer.com/news/apple/fake-paid-expert-interviews-impersonate-brands-to-steal-google-logins/)*
