---
title: "WebP Support Added to shot-scraper Screenshot Automation Tool"
slug: "webp-support-added-to-shot-scraper-screenshot-automation-tool"
description: "The screenshot automation tool shot-scraper has been updated to support the WebP image format. This new capability allows users to capture web page screenshots directly as WebP files."
date: 2026-09-14T12:02:44+05:30
tags: [shotscraper, WebP, WebPerformance, DeveloperTools]
categories: ["AI", "Developer Tools", "Software Development", "Web Development"]
author: "Shoubhik Banerjee"
draft: false
---

# WebP Support Added to shot-scraper Screenshot Automation Tool

The screenshot automation tool shot-scraper has been updated to support the WebP image format. This new capability allows users to capture web page screenshots directly as WebP files.

## 🧩 How it works

You can take a WebP screenshot of a web page by using the following command format:

```
shot-scraper https://simonwillison.net -o screenshot.webp --quality 80
```

* **Quality setting**: The `--quality` option allows you to set the quality level of the screenshot.
* **Lossless output**: If you do not use the `--quality` option, the WebP file will be lossless.

## ⚙️ Key details

* **File size efficiency**: WebP screenshots are almost always significantly smaller in file size than their JPEG or PNG equivalents.
* **Examples**: Examples of these screenshots are available in the feature's Pull Request (PR).

## 💡 Why it matters

This feature was shipped specifically to generate the screenshot for a new tool called commit-rewriter.

#shotscraper #WebP #WebPerformance #DeveloperTools

---

*Source: [Release: shot-scraper 1.12](https://simonwillison.net/2026/Sep/13/shot-scraper/)*
