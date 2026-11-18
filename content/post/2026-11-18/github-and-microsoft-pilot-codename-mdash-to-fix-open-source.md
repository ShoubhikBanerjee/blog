---
title: "GitHub and Microsoft Pilot Codename MDASH to Fix Open Source Bugs"
slug: "github-and-microsoft-pilot-codename-mdash-to-fix-open-source-bugs"
description: "In the Codename MDASH pilot, GitHub and Microsoft converted thousands of raw AI findings into 99 checked, private reports with suggested fixes for six widely used open source projects. Maintainers..."
date: 2026-11-18T06:16:59+05:30
tags: [CodenameMDASH, OpenSourceSecurity, AI, GitHub, MicrosoftSecurity]
categories: ["AI", "Cybersecurity", "Open Source", "Artificial Intelligence", "Developer Tools"]
image: "https://github.blog/wp-content/uploads/2026/11/image-17.png"
author: "Shoubhik Banerjee"
draft: false
---

# GitHub and Microsoft Pilot Codename MDASH to Fix Open Source Bugs

In the Codename MDASH pilot, GitHub and Microsoft converted thousands of raw AI findings into 99 checked, private reports with suggested fixes for six widely used open source projects. Maintainers have already fixed more than half of these vulnerabilities.

## 🧩 How it works

Codename MDASH is a multi-model agentic scanning harness from Microsoft Security designed to find and fix security vulnerabilities in widely used open source software. The process involves four distinct stages:

*   **Find:** Microsoft’s MAI Cyber model scanned each project and suggested fixes for identified vulnerabilities.
*   **Filter:** An AI triage agent from the GitHub Security Lab, built on tailored Copilot skills, removed duplicates, checked validity, and focused on high-impact bugs so maintainers did not have to review raw scan results.
*   **Report privately:** Reports reached maintainers through GitHub private vulnerability reporting, including a proof of concept and a suggested fix.
*   **Fix:** Maintainers decided what to fix, how to fix it, and when.

## ⚙️ Key details

Seven researchers spent about two days per project checking findings by hand. As of November 15, maintainers had fixed 55 vulnerabilities, with 14 of those fixes already included in a release. The first fixes shipped about a week after the initial scan.

| Project | Outcome |
| :--- | :--- |
| Caddy | Maintainers fixed all 22 reports in a week or less. |
| AutoGPT | A report on a broken check landed three days later; the fix was in production in less than a week. |
| ImageMagick | A report pointed to exact code lines; a fix was pushed in 15 minutes. |

Normally, reading, understanding, and fixing a security advisory takes 30 minutes to 1 hour on average. Codename MDASH found unknown, obscure security bugs with succinct reports and filled in gaps from prior reports that had not been noticed. For open source, fixes are delivered via private vulnerability reporting (PVR), and maintainers must run CI/CD tests on private forks to verify those fixes.

## 💡 Why it matters

AI has made finding potential vulnerabilities fast and cheap, but fixing them requires human judgment that falls to maintainers in open source. Many maintainers are already flooded with AI-generated security findings, including duplicates and reports that are not vulnerabilities. The pilot demonstrated that AI can help maintainers ship fixes rather than just handing them more findings, cutting through the noise of vulnerability reports.

![figure](https://github.blog/wp-content/uploads/2026/11/image-17.png?resize=1600%2C850)

![figure](https://github.blog/wp-content/uploads/2026/11/mdash-pilot-result-highres.png?resize=1024%2C571)

#CodenameMDASH #OpenSourceSecurity #AI #GitHub #MicrosoftSecurity

---

*Source: [Maintainers don't need more AI bug reports. They need fixes.](https://github.blog/open-source/maintainers/maintainers-dont-need-more-ai-bug-reports-they-need-fixes/)*
