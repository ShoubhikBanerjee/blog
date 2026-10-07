---
title: "Momentic AI launches intent‑based test automation platform with 99.2% reliability"
slug: "momentic-ai-launches-intentbased-test-automation-platform-with-99-2-reliability"
description: "Momentic AI announced updated capabilities for its intent‑based test automation platform, now running 200M+ test steps a month for over 2,600 users with 99.2% reliability and preventing more than..."
date: 2026-10-07T18:06:06+05:30
tags: [AITesting, Momentic, Azure, GitHubActions]
categories: ["AI", "Artificial Intelligence", "Software Testing", "Developer Tools", "Cloud Computing"]
image: "https://media.daily.dev/image/upload/s--QgMRrp8J--/f_auto,q_auto/v1/recruiter-landing/6ac440e4ef6c0279d8507e9b_1791270639463_f16a6573ec?_a=BAMAMiB80"
author: "Shoubhik Banerjee"
draft: false
---

# Momentic AI launches intent‑based test automation platform with 99.2% reliability

Momentic AI announced updated capabilities for its intent‑based test automation platform, now running 200M+ test steps a month for over 2,600 users with 99.2% reliability and preventing more than 390,000 bugs from reaching production each month.

## 🔍 Overview
- Momentic lets engineers write end‑to‑end tests in plain English.
- Tests are decomposed into locator, assertion, visual, and extraction agents.
- Agents call Claude Opus, Claude Sonnet 4.6, and OpenAI models via Microsoft Foundry.
- Execution runs on Azure infrastructure and reports through GitHub Actions or Momentic’s Model Context Protocol (MCP) server.
- An agent can invoke Momentic to run a team’s tests before a pull request is opened.

## 🛠️ Problem with legacy UI test frameworks
- Selenium, Cypress, and Playwright rely on brittle CSS selectors and hard‑coded paths.
- Selectors break with every UI change, forcing teams to maintain tests instead of shipping.
- Reliability typically stalls near 95%; false failures cause engineers to ignore alerts.
- AI coding assistants generate code faster than teams can verify, increasing the verification burden.

## 🧩 How Momentic works
- An engineer describes a flow in ordinary language; the platform infers the test intent, drives the browser, and updates element references when the UI changes.
- The plain‑English test is routed to specialized components:
  - **Locator agent** – finds elements using multi‑modal signals (screenshots, accessibility tree, network traffic).
  - **Assertion agent** – evaluates expected outcomes.
  - **Visual agent** – interprets visual state.
  - **Extraction agent** – pulls data from the page.
- These components reason over the same multi‑modal inputs rather than a single fragile selector string.

| Model | Role |
|-------|------|
| Claude Opus | Primary model for agents |
| Claude Sonnet 4.6 | Primary model for agents |
| OpenAI models | Primary model for agents |

## ⚙️ Key details & performance
- Runs **200 M+ test steps** per month for **2,600+ users**.
- Achieves **99.2% reliability**, stopping **390 k+ bugs** from reaching production each month.
- Teams automate about **70% faster** than on legacy frameworks.
- On Microsoft Foundry, onboarding a new model provider drops from weeks to **2–3 hours**.

## 🚀 Architecture & integrations
- Agents call Claude Opus, Claude Sonnet 4.6, and OpenAI models via Microsoft Foundry, an enterprise‑grade service with Azure SLAs and compliance certifications.
- Tests execute on Azure and report back via **GitHub Actions** or the **MCP server**, which wires directly into GitHub Copilot, Claude Code, and Cursor.
- An AI coding assistant (Copilot, Claude Code, Cursor) can call Momentic to validate its generated code before a human reviews the pull request.
- Results are returned for engineering review; Momentic reports on the code but does **not** approve or merge it.

## 💰 Business and funding
- Founded by **Wei‑Wei Wu** and **Jeff An** in late 2023 in San Francisco.
- Graduated from **Y Combinator W24** batch.
- Raised **$19.2 M** total: a **$3.7 M seed** round followed eight months later by a **$15 M Series A** announced in **Nov 2025**, led by **Standard Capital** with participation from **Dropbox Ventures, Y Combinator, FCVC, Transpose Platform, and Karman Ventures**.

## 🔐 Security & compliance
- Built on Microsoft Foundry, which carries Azure service‑level agreements and compliance certifications.
- Using a platform already under enterprise review shortens security and procurement conversations.
- Customers remain responsible for their own vendor, security, and procurement requirements.


#AITesting #Momentic #Azure #GitHubActions

---

*Source: [From Plain English to Passing Tests: Momentic on Microsoft Foundry with Claude | Microsoft Customer Stories](https://www.microsoft.com/en/customers/story/27404-momentic-foundry-models)*
*Source: [The best AI engineer accounts to follow on X in 2026 | daily.dev](https://daily.dev/blog/best-ai-engineer-accounts-to-follow-on-x/)*
