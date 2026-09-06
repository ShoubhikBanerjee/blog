---
title: "Claude CLI and Remote Control receive new features and numerous bug fixes"
description: "Claude’s command‑line interface and Remote Control components received a batch of new settings, commands, and a long list of stability fixes."
date: 2026-09-06T22:07:38+05:30
tags: [Claude, AItools, BugFixes, CLI, RemoteControl]
categories: [AI]
image: "https://opengraph.githubassets.com/7238f46747ad5e19ecdcaabd3270ce44ae0c6cd94376e7b854efc6ba41bfde3f/anthropics/claude-code"
author: "Shoubhik Banerjee"
draft: false
---

# Claude CLI and Remote Control receive new features and numerous bug fixes

Claude’s command‑line interface and Remote Control components received a batch of new settings, commands, and a long list of stability fixes.

## 🔧 New Features
- Added an "Organization policy" line to /status andclaude doctor that says why your organization's policy could not be loaded, such as a proxy not passing the endpoint through.
- Added `bashOutputMaxChars` and `taskOutputMaxChars` settings to raise how much command and background‑task output Claude receives inline before it is saved to a file, up to 128K characters.
- Added `--append-subagent-system-prompt-file` to read the subagent system prompt from a file, for prompts too large to pass on the command line.
- Added `/skill-doctor` to show which loaded skills go unused and what they cost in context, so you can prune them.

## 🛠️ Fixes
- Fixed typed or pasted characters occasionally landing out of order or being dropped during fast input or key repeat.
- Fixed `/add-dir <subdirectory>` printing a false "couldn't be resolved" error when the working directory is on a/net automount.
- Fixed the Bedrock setup wizard hanging when AWS or an AWS credential helper never responds; it now times out with a clear error, and its model checks now fail correctly behind a TLS‑inspecting proxy.
- Fixed cloud sessions discarding a plugin synced from claude.ai when managed settings force‑enable it in `enabledPlugins`, then falling back to a marketplace clone that could fail.
- Fixed being unable to delete the character immediately before an inline `[Image #N]` chip in the prompt input.
- Fixed resuming a session losing hook output and other context around parallel tool calls, which changed the resumed request.
- Fixed Remote Control showing a stale permission mode when a phone, browser, or claude.ai app attaches to a terminal session or after the mode changes in the terminal.
- Fixed Remote Control sessions showing as still working (stuck spinner and Stop button) after stopping a turn from a connected phone or browser, or after a local slash command like `/clear`.
- Fixed SDK and cloud sessions ignoring a Stop or interrupt sent just after the first prompt, before the turn had started; the turn now stops instead of running to completion.
- Fixed Remote Control uploading a session pulled with `/teleport` into the connected session, which appeared appended to the original on phone and web.
- Fixed Remote Control's inbound event stream failing behind TLS‑inspecting corporate proxies on native Windows.
- Fixed Remote Control sessions showing the default effort level on claude.ai when the effort comes from settings.
- Fixed `gcpAuthRefresh` opening a browser at startup when the Google credential check was slow, even though the credential was still valid.
- Fixed claude.ai connectors staying absent for the whole session when the startup connector fetch timed out — the CLI now retries in the background.
- Fixed sustained high CPU usage when a background agent could not be resumed and its wake‑up was retried in a tight loop.
- Fixed feature flags gated to a newer version occasionally applying to an older Claude Code version running on the same machine.
- Fixed `/usage` and the VS Code usage panel dropping a model‑specific weekly limit row when the usage endpoint is rate limited or when opened right after startup.
- Fixed `claude -p --resume <file>` adopting a malformed session ID recorded in the transcript; it now resumes under a fresh session ID instead.
- Fixed the terminal progress indicator (iTerm2, Ghostty, ConEmu) showing the session as finished while a background workflow or agent was still running.
- Fixed a rare layout glitch where a box could render with the wrong height after its container switched between row and column direction.
- Fixed Claude apps gateway client IP when a trusted proxy appends a port to `X-Forwarded-For`; with an access list set, an unreadable entry now gets 403.
- Fixed Claude apps gateway telling Claude Desktop to export OpenTelemetry as JSON even when the terminal CLI uses protobuf, so protobuf‑only collectors rejected Desktop's data.
- Fixed Desktop and web showing a session as busy while it only watches an artifact for updates.
- Fixed Claude in Chrome file_upload failing with "paths: expected array, received undefined" in local Cowork sessions run from the Claude Desktop app.
- Fixed SendMessage to an offline Remote Control session on another machine reading as delivered; the result now says delivery is queued until that machine reconnects.
- Fixed plugin install hints from CLIs run in background Bash commands: they are now detected, and the raw `<claude-code-hint>` tag no longer leaks into the conversation.

## 📊 Impact
These additions expand configurability (organization policy visibility, output size limits, subagent prompts, skill usage diagnostics) while the extensive bug‑fix set improves reliability across CLI, Remote Control, cloud, and integration pathways. Users can now diagnose policy loading issues, capture larger tool outputs inline, manage unused skills, and experience fewer interruptions caused by UI glitches, proxy complications, or session‑management bugs.

#Claude #AItools #BugFixes #CLI #RemoteControl

---

*Source: [Releases · anthropics/claude-code](https://github.com/anthropics/claude-code/releases)*
