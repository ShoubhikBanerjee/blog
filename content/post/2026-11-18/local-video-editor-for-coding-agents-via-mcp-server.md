---
title: "Local Video Editor for Coding Agents via MCP Server"
slug: "local-video-editor-for-coding-agents-via-mcp-server"
description: "ffmpeg-skill is an Agent Skill for Claude Code, Cursor, Codex, and any MCP client. It provides a local video editor using FFmpeg."
date: 2026-11-18T12:19:35+05:30
tags: [f, f, m, p, e, g, v, i, d, e, o, e, d, i, t, i, n, g, c, o, d, i, n, g, a, g, e, n, t, s, m, c, p, l, o, c, a, l, a, i]
categories: ["AI", "A", "I", "A", "g", "e", "n", "t", "s", ",", "V", "i", "d", "e", "o", "P", "r", "o", "c", "e", "s", "s", "i", "n", "g", ",", "O", "p", "e", "n", "S", "o", "u", "r", "c", "e", ",", "D", "e", "v", "e", "l", "o", "p", "e", "r", "T", "o", "o", "l", "s"]
image: "https://avatars.githubusercontent.com/u/20648875?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Local Video Editor for Coding Agents via MCP Server

ffmpeg-skill is an Agent Skill for Claude Code, Cursor, Codex, and any MCP client. It provides a local video editor using FFmpeg.

## 🔍 Overview

It ships 42 FFmpeg tools for tasks like cut, captions, reframe, loudness, and platform exports. The agent edits footage locally and checks its own output.

## ⚙️ Key Details

*   No cloud, no API keys
*   Uses Python standard library
*   Machine-readable contract (SPEC)
*   CLI flag-for-flag tracking via argparse

## 🧩 How it works

It teaches the agent a fixed workflow: probe → edit losslessly where possible → check → verify. Every tool is also callable as an MCP tool.

## 🚀 Availability

*   Requires ffmpeg and python3 on PATH
*   Works offline
*   Supports footage that should not be uploaded

#f #f #m #p #e #g #, # #v #i #d #e #o #e #d #i #t #i #n #g #, # #c #o #d #i #n #g #a #g #e #n #t #s #, # #m #c #p #, # #l #o #c #a #l #a #i

---

*Source: [kajisho5/ffmpeg-skill](https://github.com/kajisho5/ffmpeg-skill)*
