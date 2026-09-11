---
title: "Python 3.15 Introduces Soft Deprecation for re.match()"
slug: "python-3-15-introduces-soft-deprecation-for-re-match"
description: "Python 3.15 is introducing the soft deprecation of the re.match() function, marking it as an API that should no longer be used to write new code without a promise or threat of future removal."
date: 2026-09-11T22:04:55+05:30
tags: [Python, Programming, SoftwareDevelopment, Python315]
categories: ["AI", "Software Development", "Programming Languages"]
author: "Shoubhik Banerjee"
draft: false
---

# Python 3.15 Introduces Soft Deprecation for re.match()

Python 3.15 is introducing the soft deprecation of the re.match() function, marking it as an API that should no longer be used to write new code without a promise or threat of future removal.

## ⚙️ Key details

Python 3.15 release manager Hugo van Kemenade describes the move to soft deprecate the "venerable but deeply confusing" re.match() function. A clearer alternative has been introduced to reflect how the function anchors at the beginning of a string, but not the end.

## 🧩 How it works

Depending on the desired outcome, developers can use the following functions:

| Function | Purpose |
| :--- | :--- |
| `re.prefixmatch()` | The clearer alternative to `re.match()` |
| `re.search()` | Match a pattern anywhere in the string |
| `re.fullmatch()` | Match the entire string |

#Python #Programming #SoftwareDevelopment #Python315

---

*Source: [Soft-deprecating re.match()](https://simonwillison.net/2026/Sep/11/soft-deprecating-re-match/)*
