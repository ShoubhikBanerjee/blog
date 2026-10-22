---
title: "Wiz Research Uses AI Models to Discover PHP Remote Code Execution Vulnerabilities"
slug: "wiz-research-uses-ai-models-to-discover-php-remote-code-execution-vulnerabilities"
description: "Wiz Research discovered two remote code execution (RCE) vulnerabilities in PHP using a combination of AI tools, leading to a patched release on October 21, 2026."
date: 2026-10-22T06:10:45+05:30
tags: [PHP, WizResearch, Cybersecurity, RCE, AI]
categories: ["AI", "Artificial Intelligence", "Cybersecurity", "Software Development"]
author: "Shoubhik Banerjee"
draft: false
---

# Wiz Research Uses AI Models to Discover PHP Remote Code Execution Vulnerabilities

Wiz Research discovered two remote code execution (RCE) vulnerabilities in PHP using a combination of AI tools, leading to a patched release on October 21, 2026.

## 🔍 Overview
Wiz Research identified the vulnerabilities using the following tools:
* Wiz Atlas
* Gemini 4 Argon
* GPT-5.6 Sol

## ⚙️ Key details
The discovery process and subsequent disclosure followed this timeline:

| Date | Event |
| :--- | :--- |
| August 19, 2026 | Wiz Research discovers the first PHP vulnerability |
| August 20, 2026 | Unauthenticated RCE confirmed against Drupal |
| August 21, 2026 | Unauthenticated RCE confirmed against WordPress |
| August 24, 2026 | Vulnerabilities reported to the PHP security team |
| September 21, 2026 | PHP acknowledges reports and begins developing a fix |
| October 21, 2026 | Patched PHP releases become available and public disclosure occurs |

## 💡 Why it matters
The vulnerabilities affected the entire PHP 8.x line. Due to a leak in the coordinated disclosure process, CVE IDs began circulating on social media and forums on October 20th. This led to several developments:
* The PHP project moved the release date from October 22nd to October 21st.
* A security firm named Calif mistakenly published a video showing a proof of concept working against targets.
* The circulation of the video accelerated the development of various exploitation proof of concepts (PoCs).

#PHP #WizResearch #Cybersecurity #RCE #AI

---

*Source: [Today’s PHP Security Release, and How We’re Strengthening PHP Security](https://simonwillison.net/2026/Oct/21/php-security-release/)*
