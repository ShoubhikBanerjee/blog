---
title: "Applying Evidence-First Method to Application Modernization"
slug: "applying-evidence-first-method-to-application-modernization"
description: "A request to modernize an application often starts with a technology question: Which framework should replace the old one? Before you choose, find out what still works. This post walks through an..."
date: 2026-11-26T22:08:01+05:30
tags: []
categories: ["AI"]
image: "https://github.blog/wp-content/uploads/2026/11/38b3dc4817bfb01261d608e093dda2cdf3392f0886a14b95208bc6f1cd49e58d-1920x1080-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# Applying Evidence-First Method to Application Modernization

## 🔍 Overview

A request to modernize an application often starts with a technology question: Which framework should replace the old one? Before you choose, find out what still works. This post walks through an evidence-first method applied to four public applications, from a small Node.js game to a large Java enterprise resource planning (ERP) application.

## 🧩 How it works

The evidence-first method involves collecting evidence that can act as a regression net for behavior and showing where modernization is necessary. Each application needed a different treatment, but the way I collected evidence, chose the next experiment, and decided on possible proof points was repeatable.

## ⚙️ Key details

Before you recommend a change, build a small evidence inventory including:

- Manifests, lockfiles, entry points, and deployable components
- Verified commands for installing, building, testing, packaging, and running
- Runtime pins in containers, CI workflows, deployment files, and developer tooling
- External contracts such as APIs, database behavior, file formats, and user workflows
- End-of-life frameworks and dependencies, with evidence that the application still uses them

I use three simple labels: documented, inferred, and unverified. If two files disagree about the Java version, resolve the contradiction. If you can't determine whether a CI check blocks merges, say so. Record the unknown rather than treating a guess as a finding.

## 💡 Why it matters

Once you understand the application, make the decision per component. A single system can contain code that should stay, dependencies that should be swapped, and one subsystem that genuinely needs a rewrite. First, check whether a capability is still needed. Remove it only after verifying that it is unused or superseded and confirming that decision with its owner. For a capability you still need, start with the option that changes the least:

- Keep it. Supported code that still fits the job doesn't need a modernization story.
- Upgrade it. Move to a supported major version and fix the breaking changes.
- Swap it. Replace an abandoned dependency while preserving the existing design.
- Wrap it. Stabilize a useful interface and replace the internals in increments.
- Rewrite it. Use this when no responsible upgrade path exists or the architecture cannot meet the requirement.

---

*Source: [How to choose the next safe step in application modernization](https://github.blog/ai-and-ml/github-copilot/how-to-choose-the-next-safe-step-in-application-modernization/)*
