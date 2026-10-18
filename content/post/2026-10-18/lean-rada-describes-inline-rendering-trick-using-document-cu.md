---
title: "Lean Rada Describes Inline Rendering Trick Using document.currentScript"
slug: "lean-rada-describes-inline-rendering-trick-using-document-currentscript"
description: "On 17th October 2026, Lean Rada described a trick for inline rendering that utilizes the `document.currentScript` property. This method allows a tiny inline `<script>` element to replace itself with..."
date: 2026-10-18T18:01:54+05:30
tags: [JavaScript, WebDevelopment, Frontend, Coding, HTML]
categories: ["AI", "Web Development", "Software Engineering", "Programming"]
author: "Shoubhik Banerjee"
draft: false
---

# Lean Rada Describes Inline Rendering Trick Using document.currentScript

On 17th October 2026, Lean Rada described a trick for inline rendering that utilizes the `document.currentScript` property. This method allows a tiny inline `<script>` element to replace itself with dynamic content when a page loads.

## 🧩 How it works

The trick functions by having a script reference its own position in the document to swap itself for new data.

*   Basic Implementation: An inline script can use `document.currentScript.replaceWith(new Date().getFullYear())` to replace the tag with the current year.
*   Shortcut Function: A shortcut can be defined as `$=(...n)=>document.currentScript.replaceWith(...n)` to simplify the process.
*   Template Language: This shortcut creates a tiny template language, allowing for inline syntax such as `<script>$(new Date().getFullYear())</script>`.

## ⚙️ Key details

| Item | Description |
| :--- | :--- |
| Core Property | document.currentScript |
| Replacement Method | .replaceWith() |
| Shortcut Definition | $=(...n)=>document.currentScript.replaceWith(...n) |
| Creator | Lean Rada |

#JavaScript #WebDevelopment #Frontend #Coding #HTML

---

*Source: [Inline rendering with document.currentScript](https://simonwillison.net/2026/Oct/17/document-currentscript/)*
