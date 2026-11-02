---
title: "Resolving Python 3.15 Dependency Errors Caused by Local uv.lock Files"
slug: "resolving-python-3-15-dependency-errors-caused-by-local-uv-lock-files"
description: "Switching to Python 3.15 can cause occasional dependency errors when local `uv.lock` files pin dependency versions that lack Python 3.15 wheels."
date: 2026-11-02T12:03:18+05:30
tags: [Python, uv, PyO3, SoftwareDevelopment]
categories: ["AI", "Python", "Software Development", "Package Management"]
author: "Shoubhik Banerjee"
draft: false
---

# Resolving Python 3.15 Dependency Errors Caused by Local uv.lock Files

Switching to Python 3.15 can cause occasional dependency errors when local `uv.lock` files pin dependency versions that lack Python 3.15 wheels.

## 🔍 Overview

Running commands such as `uv run pytest` leaves `uv.lock` files in the local environment. Because these files are listed in `.gitignore`, they are not committed to repositories. However, they can cause build failures when the locked version of a dependency does not yet support Python 3.15.

## ⚙️ Key details

- **Library practices:** Most library projects omit a `uv.lock` file so they do not lock dependency versions for downstream users.
- **Error cause:** Running `uv run pytest` generates a local `uv.lock` file, which may pin a dependency version such as `watchfiles==1.1.1` that lacks a Python 3.15 wheel.
- **Build failure error:** A failure occurs during `maturin.build_wheel` because the configured Python interpreter version (3.15) is newer than PyO3's maximum supported version (3.14).

## 💡 Resolution

When encountering this error, deleting the `uv.lock` file and running `uv run pytest` again usually fixes the problem.

#Python #uv #PyO3 #SoftwareDevelopment

---

*Source: [If in doubt, delete the uv.lock file](https://simonwillison.net/2026/Nov/1/delete-uv-lock-first/)*
