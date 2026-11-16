---
title: "Browser Use releases Pi Mono-based web agent with cloud browser support"
slug: "browser-use-releases-pi-mono-based-web-agent-with-cloud-browser-support"
description: "Browser Use has announced a new AI web agent built on Pi Mono, described as a tiny TypeScript web agent that hill climbed on real browser evaluations. The agent writes JavaScript, controls Chrome,..."
date: 2026-11-16T22:14:27+05:30
tags: [AIagents, TypeScript, webautomation, PiMono, BrowserAutomation]
categories: ["AI", "AI Agents", "Web Development", "Automation", "Cloud Services"]
image: "https://avatars.githubusercontent.com/u/192012301?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Browser Use releases Pi Mono-based web agent with cloud browser support

Browser Use has announced a new AI web agent built on Pi Mono, described as a tiny TypeScript web agent that hill climbed on real browser evaluations. The agent writes JavaScript, controls Chrome, and builds the helpers it needs dynamically. It uses Pi Mono plus a persistent V8 REPL and raw CDP to enable programmability with sessions, saved logins, streaming and typed results. The implementation is provided as a single SDK that can be integrated into applications via npm install @browser_use/pi, pnpm add @browser_use/pi, or bun add @browser_use/pi. Developers need Node 22.19+ or Bun 1.3.14+ (with Bun requiring Node for the V8 worker). The system uses Browser Use Cloud, so no local Chrome installation is needed, and supports upstream Pi's model catalog and transports with custom providers, sessions with follow-ups and saved logins, persistent workspaces, and cloud browsers or user-owned Chrome. An ultrafast mode minimizes waits after actions, and the platform provides interaction highlights, recordings, and GIF exports. JavaScript runs in a separate worker with filesystem and network access, while anonymous run counters are enabled by default but can be disabled through telemetry settings or the DO_NOT_TRACK environment variable.

#AIagents #TypeScript #webautomation #PiMono #BrowserAutomation

---

*Source: [browser-use/browser-use-pi](https://github.com/browser-use/browser-use-pi)*
