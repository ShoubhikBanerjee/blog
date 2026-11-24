---
title: "Analysis of 5,400 Malicious NPM Packages Reveals Evolving Supply Chain Tactics"
slug: "analysis-of-5-400-malicious-npm-packages-reveals-evolving-supply-chain-tactics"
description: "In this first part, we analyzed approximately 5,400 confirmed malicious npm packages published between December 2025 and October 2026, the first year following npm's revocation of long-lived..."
date: 2026-11-24T12:08:32+05:30
tags: [npmSecurity, SupplyChainAttack, MalwareAnalysis, ThreatIntelligence, OpenSource]
categories: ["AI", "Cybersecurity", "Software Supply Chain", "Threat Intelligence", "Development Tools"]
image: "https://www.databricks.com/sites/default/files/2026-11/cover-notext.png"
author: "Shoubhik Banerjee"
draft: false
---

# Analysis of 5,400 Malicious NPM Packages Reveals Evolving Supply Chain Tactics

In this first part, we analyzed approximately 5,400 confirmed malicious npm packages published between December 2025 and October 2026, the first year following npm's revocation of long-lived authentication tokens. The dataset comprises packages detected by a scanner that analyzes npm publish events for suspicious packages, with results filtered for precision by retaining only packages with at least one independent source, such as a public advisory, a vendor-published campaign report, an npm security takedown, or analyst review. Time is measured by npm publish date, and the unit of record is the package version, dated by its first malicious version.

## 🔍 Threat Landscape Overview
Monthly counts of confirmed malicious packages vary by a factor of fifteen across the period. Activity remains stable with several hundred new publisher accounts per month and a flat rate of malicious packages relative to total packages published. In August 2026, a single dependency-confusion campaign accounts for 78% of confirmed versions. Dependency-confusion reconnaissance is continuous, present in every month at a consistent level, while compromise of legitimate packages is episodic.

## 🧩 Attack Vectors and Campaigns
Three waves of a single worm family occurred in May, June, and August 2026. The May and August waves each compromised more than one hundred packages, and the June wave republished a vendor's entire scope in one day. 

*   **Token Theft Shift:** Classic long-lived tokens were revoked on December 9, 2025. Theft of npm authentication tokens peaked at 22% of packages in March 2026 and fell below 5% from May. The tokens targeted in this period were plausibly granular access tokens and CI secrets.
*   **Obfuscation:** The share of actors whose packages trigger an obfuscation rule more than doubled between May and August 2026. 72% of packages have an obfuscation marker, and 30% retrieve a second stage.
*   **Compromised Packages:** 78% of compromised versions add or modify a lifecycle script, compared with 4% of attacker-created packages. 23% show a change of maintainer or publisher, but the majority of compromises are published through the legitimate account and leave ownership records unchanged.

## ⚙️ Attacker Profile and Package Characteristics
99% of malicious packages are published by single-maintainer accounts, and 55% of accounts use a free-mail address. Two-thirds of accounts publish exactly one malicious package; among those publishing more than one, the median interval from first to last malicious publish is under one day.

*   **DPRK-nexus Campaigns:** These are the exception, operating several hundred accounts at one to two packages each, with 83% on free-mail addresses.
*   **Other Named Campaigns:** These use free-mail addresses in 15% of cases, consistent with procured account pools.
*   **Package Traits:** 88% of packages are under thirty days old at the malicious publish, 75% declare no repository, and 65% retain npm init template values in the author, description, or repository fields. 54% declare a lifecycle script, and 17% carry an internal-looking name (core, utils, sdk, config). Typosquatting is a minority tactic, with 13% embedding a popular package name and under 5% being within two character edits of one.

## 💡 Payload Behavior and Targeting
Credential and data theft is the predominant behavior in every month, except August. In August, a significant number of packages stole credentials but ultimately aimed to deliver a Sliver command-and-control implant on the victim machine, changing their classification to Trojan / Downloader.

*   **Credential Targets:** 45% of credential stealers target a single credential class, while 36% target three or more. Single-class stealers are distributed evenly across cloud credentials, SSH keys, AI-developer credentials, npm tokens, and .env files. In multi-class stealers, cloud credentials, SSH keys, and .env files co-occur; wallet and browser-data theft occur separately.
*   **AI Developer Credentials:** Targeting remained at 1-4% of packages throughout the year, but absolute counts rose with volume. AI-developer credentials are the most specialized target: 80% of packages that target them target no other class.
*   **OS Specificity:** 55% of packages contain no operating-system-specific code. Droppers target Windows (PowerShell, scheduled tasks, executables), while credential stealers and backdoors target Linux (systemd, cron, shell configuration files). macOS-specific code appears in approximately one in eight stealers.
*   **Scoped Packages:** 24% of packages are scoped, across more than three hundred distinct scopes, most of which contain a single malicious package.

![figure](https://www.databricks.com/sites/default/files/blog_images/the-2026-npm-threat-landscape-blog-img-1.png)

![figure](https://www.databricks.com/sites/default/files/blog_images/the-2026-npm-threat-landscape-blog-img-2.png)

![figure](https://www.databricks.com/sites/default/files/blog_images/the-2026-npm-threat-landscape-blog-img-3.png)

#npmSecurity #SupplyChainAttack #MalwareAnalysis #ThreatIntelligence #OpenSource

---

*Source: [What 5,400 Malicious npm Packages Reveal about Software Supply Chain Risk in 2026](https://www.databricks.com/blog/what-5400-malicious-npm-packages-reveal-about-software-supply-chain-risk-2026)*
