---
title: "Community Agent Skill Restores Codex Desktop Capabilities on Windows"
slug: "community-agent-skill-restores-codex-desktop-capabilities-on-windows"
description: "A new community-maintained Agent Skill has been released to guide AI assistants in restoring local patches and capability switches for Codex Desktop on Windows following updates. This tool provides..."
date: 2026-11-18T22:09:17+05:30
tags: [C, o, d, e, x, W, i, n, d, o, w, s, A, g, e, n, t, S, k, i, l, l, s, O, p, e, n, S, o, u, r, c, e, D, e, v, T, o, o, l, s]
categories: ["AI", "A", "I", "A", "g", "e", "n", "t", "s", ",", "S", "o", "f", "t", "w", "a", "r", "e", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t", ",", "W", "i", "n", "d", "o", "w", "s", ",", "O", "p", "e", "n", "S", "o", "u", "r", "c", "e"]
image: "https://avatars.githubusercontent.com/u/255150494?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Community Agent Skill Restores Codex Desktop Capabilities on Windows

A new community-maintained Agent Skill has been released to guide AI assistants in restoring local patches and capability switches for Codex Desktop on Windows following updates. This tool provides diagnostic workflows and repair scripts to fix issues such as missing model lists, browser functionality, and computer control features.

## 🔍 Overview
- **Purpose:** Guides agents to restore local patches and capability switches after updates.
- **Scope:** Fixes model lists, browser, and computer control (computer use) features.
- **Nature:** Community-maintained Agent Skill (diagnosis + scripts), not an official client or universal installer.
- **Platform:** Windows only.

## 🛠️ Installation
- **Prerequisites:** Windows Codex Desktop, Git, and an AI assistant that supports Agent Skills.
- **Setup Command:**
  ```bash
  $SkillRoot = "$env:USERPROFILE\.codex\skills\codex-windows-fast-patch"
  git clone https://github.com/chen0416ccc-cpu/codex-windows-fast-patch-skill.git $SkillRoot
  ```
- **Paths:**
  - Standard: `$env:USERPROFILE\.codex\skills\codex-windows-fast-patch`
  - Claude Code: `$env:USERPROFILE\.claude\skills\codex-windows-fast-patch`
- **Activation:** Restart the AI assistant to load the skill. The skill updates automatically before use.

## 🧩 Capabilities & Fixes
- **Proxy Restoration:** Restores CUA browser proxy settings. It inherits valid `HTTP_PROXY`/`HTTPS_PROXY` or generates a managed local runtime patch from Windows system proxies.
- **Mobile Control:** Optional process. If only the settings entry is missing, a dry-run script can check the route without fixing auth.
- **General Repairs:** Fixes model lists, browser, and computer control. Some fixes require reinstalling Codex.
- **Limitations:**
  - Does not support PAC, authenticated, or non-HTTP proxies.
  - Models are provided by the vendor; the project does not provide API or quotas.
  - Cannot recover deleted project files.

## ⚙️ Safety & Execution
- **Process:** The application may close during repairs, interrupting the conversation. Restart Codex and send "继续" to resume.
- **Verification:** Requires a restart and separate verification of Chrome and the built-in browser.
- **Execution Mode:** Default is background read-only verification.
- **Safety:** Does not automatically open test apps (like calculator), switch focus, or send mouse/keyboard input.
- **Reporting:** Runtime, plugin, and window enumeration checks are reported. Real screenshots and native input are only performed upon explicit request or agreement.

#C #o #d #e #x #, # #W #i #n #d #o #w #s #, # #A #g #e #n #t #S #k #i #l #l #s #, # #O #p #e #n #S #o #u #r #c #e #, # #D #e #v #T #o #o #l #s

---

*Source: [chen0416ccc-cpu/codex-windows-fast-patch-skill](https://github.com/chen0416ccc-cpu/codex-windows-fast-patch-skill)*
