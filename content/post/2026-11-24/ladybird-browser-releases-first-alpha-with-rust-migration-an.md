---
title: "Ladybird Browser Releases First Alpha with Rust Migration and Performance Gains"
slug: "ladybird-browser-releases-first-alpha-with-rust-migration-and-performance-gains"
description: "The Ladybird project has released its first alpha version, allowing users on macOS and Linux to install the browser without the need for manual compilation. This project aims to build a new browser..."
date: 2026-11-24T22:08:41+05:30
tags: [Ladybird, Browser, Rust, WebAssembly, OpenSource]
categories: ["AI", "Web Browsers", "Software Engineering", "Programming Languages"]
image: "https://static.simonwillison.net/static/2026/ladybird-ffmpeg.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Ladybird Browser Releases First Alpha with Rust Migration and Performance Gains

The Ladybird project has released its first alpha version, allowing users on macOS and Linux to install the browser without the need for manual compilation. This project aims to build a new browser by 2026 with its own implementation of core components including HTML parsing, CSS, layout, and JavaScript.

## 🔍 Overview
Ladybird is a new browser implementation that builds most of its key components internally while utilizing a few established external libraries for specific tasks.

| Component | External Library |
| :--- | :--- |
| Text shaping | HarfBuzz |
| 2D graphics | Skia |
| Video | ffmpeg |
| Database | SQLite |

## 🧩 How it works
The browser architecture focuses on isolation and parallel execution to manage web content efficiently.
*   **Process Isolation:** Ladybird runs different tabs in different processes, an isolation mechanism used by most modern browsers.
*   **Threading:** The project has moved style and layout tasks to their own dedicated thread.
*   **WebAssembly Engine:** The browser replaced its C++ WebAssembly engine with Cranelift, achieving a 7x performance boost on the JetStream 3 WASM benchmark.

## ⚙️ Key details
Significant technical milestones have been reached through AI-assisted development and rigorous testing:
*   **Rust Migration:** On February 23, 2026, Andreas Kling reported that parts of the LibJS JavaScript engine were ported from C++ to 25,000 lines of Rust in two weeks using Claude Code and Codex.
*   **Web Standards Success:** The browser gained 75,650 new passes on the web-platform-tests suite, surpassing Safari. The browser now passes approximately 2.18 million subtests.
*   **Rapid Development:** Most testing gains occurred between October 22 and October 27, 2026. This followed the release of Claude Opus 5.5 on September 22, 2026, and preceded the release of Claude Fable 5.2 on November 9, 2026.
*   **Monthly Gains:** The project recorded gains of 30,000 in /css and 10,000 in /editing tests within a single month.

## 🚀 Availability
Pre-compiled binaries for the first alpha are now available for macOS and Linux.
*   **Stability:** As an alpha software, the browser may crash or fail to load some websites.
*   **Reporting:** Users can report broken sites from within the browser and have the option to send crash reports after a failure.
*   **Security Testing:** The developers are inviting security researchers to hack the browser to help harden the system, noting that no security promises are made during this alpha stage.

![figure](https://static.simonwillison.net/static/2026/ladybird-contributions.webp)

![figure](https://static.simonwillison.net/static/2026/newsletter-oct-2026-wpt-light.webp)

#Ladybird #Browser #Rust #WebAssembly #OpenSource

---

*Source: [Ladybird’s first alpha release](https://simonwillison.net/2026/Nov/23/ladybird/)*
