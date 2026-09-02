---
title: "Paint.NET ships reverse-engineered Direct2D for WINE"
description: "Paint.NET has overcome a long-standing compatibility hurdle by shipping an internal, clean-room rewrite of Direct2D for use on WINE."
date: 2026-09-02T12:02:38+05:30
tags: [PaintNET, Direct2D, WINE, reverseengineering, compatibility]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Paint.NET ships reverse-engineered Direct2D for WINE

Paint.NET has overcome a long-standing compatibility hurdle by shipping an internal, clean-room rewrite of Direct2D for use on WINE.

## 🔍 Overview

- Direct2D has historically been the largest blocker for running Paint.NET on WINE.
- Past efforts to implement Direct2D compatibility were insufficient for Paint.NET’s needs.
- The team could not simply disable Direct2D usage in the application.

## 🧩 How it works

- Paint.NET now includes a reverse-engineered implementation of Direct2D triggered by the `/wine` command-line flag.
- The code lives in `PaintDotNet.Windows.Direct2D1.Managed.dll`.
- The rewrite was produced by a reverse-engineering assistant referred to as "Claude."

## ⚙️ Key details

- The codebase totals roughly 180,000 lines, compared to about 700,000 lines for the rest of Paint.NET.
- Development spanned multiple years, with the author noting over two decades of work on Paint.NET itself.
- The assistant operated with high productivity at times, described as "the fury of 10 freshly unshackled Einstein genius-level 10x coders."

### Code quality and maintenance

- Most of the reverse-engineered code was written in a "vibe coded" style, meaning it has not undergone thorough review.
- The author could not realistically review the full 180,000 lines of code.
- Resource management issues were identified and corrected, including missing COM reference counting (AddRef equivalents).
- Architectural and design flaws were occasionally corrected after being flagged by the author.

### Technical achievements

- The assistant performed extensive reverse engineering to derive formulas for Direct2D’s built-in effects library.

## 🚀 Availability

- The feature is available now when running Paint.NET with the `/wine` flag on WINE.

## 💡 Why it matters

- This workaround enables Paint.NET to run on WINE without relying on incomplete or unavailable Direct2D implementations.
- It demonstrates a practical path for applications to bypass platform-specific graphics limitations through clean-room reverse engineering.

#Paint.NET #Direct2D #WINE #reverseengineering #compatibility

---

*Source: [A quote from Rick Brewster](https://simonwillison.net/2026/Sep/2/rick-brewster/)*
