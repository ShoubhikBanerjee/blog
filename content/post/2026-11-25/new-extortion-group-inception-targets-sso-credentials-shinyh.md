---
title: "New Extortion Group Inception Targets SSO Credentials; ShinyHunters Claims Return"
slug: "new-extortion-group-inception-targets-sso-credentials-shinyhunters-claims-return"
description: "A newly formed data extortion group named 'Inception' has been linked to a large-scale campaign targeting single sign-on (SSO) credentials of multiple global brands. The gang surfaced on November 17,..."
date: 2026-11-25T22:10:10+05:30
tags: [ShinyHunters, Inception, SSO, DataExtortion, Phishing, Okta]
categories: ["AI", "Cybersecurity", "Data Extortion", "Phishing", "Threat Intelligence"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/24/inception.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# New Extortion Group Inception Targets SSO Credentials; ShinyHunters Claims Return

## 🕵️ Inception Targets Global Brands

A newly formed data extortion group named 'Inception' has been linked to a large-scale campaign targeting single sign-on (SSO) credentials of multiple global brands. The gang surfaced on November 17, claiming seven victims on its extortion site, including chip maker AMD, PepsiCo, Cigna Healthcare, AutoZone, and Lucid Motors. However, none of these companies have publicly confirmed a data breach.

Cybersecurity company ReversingLabs has tracked the group's activity since late October, identifying an extensive infrastructure that includes 21 domains used for SSO phishing, 41 domains believed to be part of the campaign infrastructure, and 4 other domains with suspected use. This infrastructure impersonates dozens of major corporations, including Dropbox, Duolingo, Western Union, Indeed, Activision Blizzard, Riot Games, Twitch, Reddit, Nestlé, Anthropic, Nintendo, Starbucks, McDonald's, Paramount, and NBCUniversal. The existence of these domains does not prove those firms have been breached or targeted yet.

## ⚙️ Tactics and Infrastructure

The Inception campaign appears to rely on phone-based social engineering rather than email phishing, strongly resembling tactics used by the ShinyHunters extortion group. The actors use legal-themed websites that imitate corporate authentication services, primarily Okta but also NetIQ/OpenText Access Manager.

| Component | Details |
| :--- | :--- |
| **Phishing Domains** | 21 domains identified by ReversingLabs |
| **Infrastructure Domains** | 41 domains believed to be used in the campaign |
| **Suspected Domains** | 4 additional domains with suspected use |
| **Impersonated Brands** | Includes Dropbox, Duolingo, Western Union, and Nintendo |
| **Authentication Services** | Okta, NetIQ/OpenText Access Manager |

Okta published a report linking Inception to threat cluster O-UNC-053, which was previously associated with ShinyHunters and active since March. According to Okta, after law enforcement disrupted ShinyHunters, O-UNC-053 continued to register new phishing domains. In late October, the cluster launched a legal-themed campaign, and in mid-November, the Inception leak site went live. Okta assessed that the cluster very likely changed its brand affiliation, maintaining consistent infrastructure and TTPs.

Inception responded to these links by claiming on its extortion page that it operates independently and has no affiliation to previous groups. The actors argued that overlapping targets and common domain registration services do not establish operational links, noting that private tooling circulates among independent threat actors.

## 📢 ShinyHunters Reemerges

Following a series of arrests targeting alleged ShinyHunters members, the group claimed to have returned on November 23 via a new Tor site. The site contains messages in Russian and English announcing the group's return and distancing itself from alleged impostors. The operators denounced a former member, reportedly arrested and cooperating with law enforcement, and mocked other individuals tied to the investigation, including Umbreon and Canadian cybersecurity executive Edward Dubrovsky.

To verify their identity, the new operators published two verification messages signed using historical ShinyHunters PGP keys dating back to 2020. BleepingComputer confirmed that both messages were signed using known PGP keys associated with the group, indicating access to the private signing keys. However, these keys do not confirm that the individuals behind the new operation are the same people who previously controlled the group, as the keys have circulated among numerous people. The operators stated they plan to launch a new CDN for hosting stolen data and will communicate exclusively through a specific Exploit hacking forum account and the new Tor site.

## 🛡️ Defending Against the Threat

ReversingLabs recommends enforcing phishing-resistant authentication, including FIDO2 security keys and passkeys, and strengthening help desk identity verification procedures to defend against the Inception campaign. Security teams should carefully review DNS, proxy, and identity provider logs dating back to October 21, 2026, for signs of suspicious activity.

![figure](https://www.bleepstatic.com/images/news/security/attacks/s/shinyhunters/return/shinyhunters-return-message.jpg)

#ShinyHunters #Inception #SSO #DataExtortion #Phishing #Okta

---

*Source: [New Inception extortion gang launches large-scale vishing campaign](https://www.bleepingcomputer.com/news/security/new-inception-extortion-gang-launches-large-scale-vishing-campaign/)*
*Source: [ShinyHunters claims to return after FBI arrests, uses old PGP keys as proof](https://www.bleepingcomputer.com/news/security/shinyhunters-resurfaces-after-fbi-arrests-uses-old-pgp-keys-as-proof/)*
