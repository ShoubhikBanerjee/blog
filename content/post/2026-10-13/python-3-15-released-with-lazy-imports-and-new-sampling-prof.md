---
title: "Python 3.15 Released with Lazy Imports and New Sampling Profiler"
slug: "python-3-15-released-with-lazy-imports-and-new-sampling-profiler"
description: "Python 3.15 has been released, introducing significant updates to import behavior, profiling tools, and language syntax. This release, curated by 3.14 and 3.15 release manager Hugo van Kemenade,..."
date: 2026-10-13T12:06:26+05:30
tags: [Python, Programming, SoftwareDevelopment, Python315]
categories: ["AI", "Programming Languages", "Software Development", "Technology"]
image: "https://static.simonwillison.net/static/2026/profiler-output.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Python 3.15 Released with Lazy Imports and New Sampling Profiler

Python 3.15 has been released, introducing significant updates to import behavior, profiling tools, and language syntax. This release, curated by 3.14 and 3.15 release manager Hugo van Kemenade, focuses on reducing startup costs and improving system insights.

## 🧩 How it works

Python 3.15 introduces several functional improvements to the standard library and language core:

*   **Explicit Lazy Imports (PEP 810):** Modules can now be imported using `lazy import json` or `lazy from pathlib import Path`. The module is only imported the first time a symbol is used in the code. This feature directly addresses the startup cost of heavy dependencies; for instance, installing plugins using `sentence_transformers` can add seconds to command invocations without lazy loading.
*   **Unpacking in Comprehensions (PEP 798):** A new syntax `[*sublist for sublist in lists]` allows for unpacking within comprehensions. Proposed by Adam Hartz and Erik Demaine, this is an extension of the unpacking syntax introduced in PEP 448.
*   **Tachyon Sampling Profiler:** A new sampling profiler called Tachyon (available as `profiling.sampling`) joins the standard library. Unlike tracing profilers, it periodically captures stack traces from running processes, allowing for low-overhead insights into running systems. Users can attach it to an existing process via its PID, such as using `sudo uv run --python 3.15 python -m profiling.sampling attach 1234`.

## ⚙️ Key details

The release includes several updates to the SQLite module and existing utilities:

| Feature | Description |
| :--- | :--- |
| `profiling.tracing` | The new name for the existing `cProfile` tracing profiler. |
| `blobopen()` | Efficient mechanism for partial reads and writes of large SQLite BLOB binary values. |
| `create_window_function()` | Allows creating custom SQLite window functions using a class with step, value, inverse, and finalize methods. |
| `setlimit()` / `getlimit()` | Exposes a mechanism for setting SQLite runtime limits from Python. |
| `set_authorizer(None)` | Provides a method to remove an existing SQLite authorizer. |
| `datetime.UTC` | An alias for `datetime.timezone.utc` (originally introduced in 3.11). |

## 🔍 Overview

Performance testing of the 3.15.0rc3 release by Miguel Grinberg shows that speed remains mostly consistent with Python 3.14. However, the experimental JIT demonstrated a 1.2x boost over the standard interpreter in a Fibonacci test, marking a meaningful performance increase for the JIT. 

With the arrival of Python 3.15, Python 3.10 (released in 2021) is officially no longer supported. The Tachyon profiler also introduces advanced visualization capabilities, including the ability to produce flame graphs, heat maps, and formats compatible with the Firefox profiler UI.

#Python #Programming #SoftwareDevelopment #Python315

---

*Source: [Hello Python 3.15, goodbye 3.10, and now I can use 3.11](https://simonwillison.net/2026/Oct/12/python-3-15/)*
