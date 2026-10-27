---
title: "Webframe: Go Tool for Running Web Pages as Programs"
slug: "webframe-go-tool-for-running-web-pages-as-programs"
description: "Jeff Lindsay released **webframe**, a Go project that lets you run a web page like a program. It executes the page in a hidden headless web view, streaming `console.log()` output to standard output..."
date: 2026-10-27T18:02:05+05:30
tags: [webframe, Go, WebScraping, Sandboxing]
categories: ["AI", "Software Development", "Web Scraping", "Programming Languages", "Security"]
author: "Shoubhik Banerjee"
draft: false
---

# Webframe: Go Tool for Running Web Pages as Programs

Jeff Lindsay released **webframe**, a Go project that lets you run a web page like a program. It executes the page in a hidden headless web view, streaming `console.log()` output to standard output and routing exceptions to standard error.

## 🔍 Overview
- Runs any URL or local file as a program.
- Outputs JavaScript `console.log()` to stdout.
- Sends JavaScript exceptions to stderr.
- Compared to the author’s own *shot‑scraper* tool, webframe is a much smaller package and does not rely on Playwright.

## 🧩 How it works
- Implemented in Go, built on the **glaze** library.
- **glaze** accesses the system‑installed browser engine, so webframe does not bundle its own engine.
- Supported system browsers:
  
  | Operating System | System Browser |
  |------------------|----------------|
  | macOS            | WKWebView      |
  | Linux            | WebKitGTK      |
  | Windows          | WebView2       |

## ⚙️ Key details
- Project URL: https://github.com/tractordev/webframe
- Designed to run headlessly; the browser view is hidden.
- Provides a lightweight alternative for tasks that traditionally use larger frameworks such as Playwright.

## 🚀 Evaluation as a sandboxing tool
- Claude Opus 5.5 was prompted to explore the repository, build exploratory prototypes, and assess webframe’s suitability as a sandboxing environment.
- The prompt asked the model to “put it through its paces” and evaluate security‑related aspects, though specific outcomes are not detailed in the source.

## 📡 Evaluation as a scraping tool
- The same Claude Opus 5.5 prompt also asked the model to evaluate webframe for scraping web pages using patterns similar to the *shot‑scraper* JavaScript command (see `simonw/shot‑scraper` on GitHub).
- The evaluation aimed to compare webframe’s scraping capabilities against the existing shot‑scraper approach, focusing on its minimal footprint and lack of Playwright dependency.


#webframe #Go #WebScraping #Sandboxing

---

*Source: [Research: webframe: evaluated as a scraper and a sandbox](https://simonwillison.net/2026/Oct/26/webframe-evaluation/)*
