---
title: "Independent Researchers Use Claude Opus to Access OpenAI Employee Accounts"
slug: "independent-researchers-use-claude-opus-to-access-openai-employee-accounts"
description: "A team of three independent security researchers from Hacktron gained access to OpenAI employee accounts by leveraging Anthropic’s Claude Opus 4.8 and 5. The researchers exploited a vulnerability in..."
date: 2026-09-18T22:02:10+05:30
tags: [OpenAI, Cybersecurity, Claude, BugBounty]
categories: ["AI", "Artificial Intelligence", "Cybersecurity", "Technology"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/STKS533_AI_AGENTS_HACKING_D.png?quality=90&strip=all&crop=0%2C9.9676601489831%2C100%2C80.064679702034&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Independent Researchers Use Claude Opus to Access OpenAI Employee Accounts

A team of three independent security researchers from Hacktron gained access to OpenAI employee accounts by leveraging Anthropic’s Claude Opus 4.8 and 5. The researchers exploited a vulnerability in Discourse, a third-party service used for OpenAI's community forums, to gain unauthorized entry.

## 🧩 How it works
* The researchers exploited a vulnerability in the system Discourse uses to process HEIF images.
* The team used a corrupted image file combined with forum software to execute the exploit.
* By achieving Remote Code Execution (RCE) on Discourse Cloud, they were able to pivot into the OpenAI instance.

## ⚙️ Key details
* The operation, dubbed the “HEIF Heist,” was successfully adapted to target multiple companies within one or two days.
* Although the team gained access to an employee’s Codex account and sent a pull request to prove it, they did not access the code within OpenAI’s “Monorepo.”
* The effort reportedly cost less than $3,000 in AI tokens.
* Hacktron reported the vulnerabilities to Discourse and OpenAI, both of which have since issued fixes.
* OpenAI paid Hacktron $6,500 for the bug report.

## 🚀 Affected organizations
The project was adapted to target the following entities:

| Target | Status |
| :--- | :--- |
| OpenAI | Detected/Fixed |
| Shopify | Detected |
| Slack | Target |
| Meta | Target |
| GitHub Ent | Target |
| Rails | Target |
| Next.js | Target |
| ImageMagick | Target |

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/STKS533_AI_AGENTS_HACKING_D.png?quality=90&strip=all&crop=0.95588235294118%2C0%2C98.088235294118%2C100&w=2400)

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/05/STKB364_CLAUDE_2_C_96d15c.jpg?quality=90&strip=all&crop=0%2C0%2C100%2C100&w=2400)

#OpenAI #Cybersecurity #Claude #BugBounty

---

*Source: [Security researchers used Claude to help them hack into OpenAI](https://www.theverge.com/ai-artificial-intelligence/997444/openai-hack-claude-heif-heist)*
