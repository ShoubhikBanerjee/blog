---
title: "ttok CLI tool receives first update in years, adds model listing"
slug: "ttok-cli-tool-receives-first-update-in-years-adds-model-listing"
description: "On 8 October 2026, the ttok command‑line interface (CLI) tool for counting tokens was updated after a period of inactivity."
date: 2026-10-09T12:11:21+05:30
tags: [OpenAI, CLI, TokenCounting, tiktoken]
categories: ["AI", "Developer Tools", "Natural Language Processing", "Open Source"]
author: "Shoubhik Banerjee"
draft: false
---

# ttok CLI tool receives first update in years, adds model listing

On 8 October 2026, the ttok command‑line interface (CLI) tool for counting tokens was updated after a period of inactivity.

## ⚙️ Key details
- Fixed a Click warning.
- Updated continuous‑integration (CI) configuration.
- Added a `--list-models` command to list available models.

## 🛠️ How it works
- ttok uses OpenAI's open source **tiktoken** library to count tokens.
- It can be run with **uvx**, allowing token counting in piped input streams, e.g.:

```bash
cat file.txt | uvx ttok
```

## 🚀 Availability
- The tool runs via uvx without needing a separate installation step.
- The new `--list-models` flag reveals which models are supported.

#OpenAI #CLI #TokenCounting #tiktoken

---

*Source: [Release: ttok 0.4](https://simonwillison.net/2026/Oct/8/ttok/)*
