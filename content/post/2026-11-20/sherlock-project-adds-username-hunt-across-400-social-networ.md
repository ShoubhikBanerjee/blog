---
title: "Sherlock Project Adds Username Hunt Across 400+ Social Networks"
slug: "sherlock-project-adds-username-hunt-across-400-social-networks"
description: "The Sherlock Project has expanded its capabilities to hunt down social media accounts by username across 400+ networks. However, community packages for ParrotOS and Ubuntu 24.04 are broken, so users..."
date: 2026-11-20T18:09:02+05:30
tags: [SherlockProject, SocialMedia, OpenSource, CommandLine]
categories: ["AI", "Open Source", "Command Line Tools", "Social Media Monitoring", "Software Packaging"]
image: "https://avatars.githubusercontent.com/u/48293496?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Sherlock Project Adds Username Hunt Across 400+ Social Networks

The Sherlock Project has expanded its capabilities to hunt down social media accounts by username across 400+ networks. However, community packages for ParrotOS and Ubuntu 24.04 are broken, so users are advised to use uv/pipx/pip or Docker. Community-maintained packages are available for Debian (>=13), Ubuntu (>=22.10), Homebrew, Kali, and BlackArch, though these are not directly supported or maintained by the Sherlock Project.

## 🔍 Overview
- Hunt down social media accounts by username across 400+ social networks

## 💻 Installation Options
- Community-maintained packages are available for Debian (>= 13), Ubuntu (>= 22.10), Homebrew, Kali, and BlackArch
- Packages for ParrotOS and Ubuntu 24.04, maintained by a third party, appear to be broken
- Users of these systems should defer to uv/pipx/pip or Docker
- These packages are not directly supported or maintained by the Sherlock Project

## 📂 Output and File Handling
- Accounts found will be stored in an individual text file with the corresponding username (e.g. user123.txt)
- `--output OUTPUT, -o OUTPUT` saves result to specified file (single username)
- `--folderoutput FOLDEROUTPUT, -fo FOLDEROUTPUT` saves results to folder (multiple usernames)
- `--csv` creates a CSV file
- `--xlsx` creates an Excel spreadsheet
- `--txt` enables creation of a txt file

## 🛠️ Command-line Options
| Option | Description |
|--------|-------------|
| `--verbose, -v, -d, --debug` | Display extra debugging information and metrics |
| `--site SITE_NAME` | Limit analysis to just the listed sites |
| `--proxy PROXY_URL, -p PROXY_URL` | Make requests over a proxy |
| `--dump-response` | Dump HTTP response to stdout for debugging |
| `--json JSON_FILE, -j JSON_FILE` | Load data from a JSON file or online valid JSON |
| `--timeout TIMEOUT` | Time (in seconds) to wait for response (Default 60) |
| `--print-all` | Output sites where username not found |
| `--print-found` | Output sites where username found (also if exported) |
| `--no-color` | Don't color terminal output |
| `--browse, -b` | Browse to all results in default browser |
| `--local, -l` | Force use of local data.json file |
| `--nsfw` | Include checking of NSFW sites from default list |
| `--ignore-exclusions` | Ignore upstream exclusions (may return more false positives) |

## 🔍 Username Matching
- `USERNAMES` parameter: one or more usernames to check
- Check similar usernames using `{?}` (replace to `_`, `-`, `.`)

## 🎯 Usage Notes
- The tool is primarily designed for command-line use; output can be directed to text, CSV, Excel, or browser.
- For bulk searches, use `--folderoutput` to organize results.

#SherlockProject #SocialMedia #OpenSource #CommandLine

---

*Source: [sherlock-project/sherlock](https://github.com/sherlock-project/sherlock)*
