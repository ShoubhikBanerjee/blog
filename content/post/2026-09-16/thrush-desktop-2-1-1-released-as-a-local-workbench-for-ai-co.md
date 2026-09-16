---
title: "Thrush Desktop 2.1.1 Released as a Local Workbench for AI Coding"
slug: "thrush-desktop-2-1-1-released-as-a-local-workbench-for-ai-coding"
description: "Thrush Desktop 2.1.1 has been released as a local desktop workbench for AI coding. The application combines projects, conversations, file review, and coding agents into a single desktop application."
date: 2026-09-16T18:03:35+05:30
tags: [AICoding, Docker, Git, ThrushDesktop, AIAgents]
categories: ["AI", "AI Agents", "Software Development", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/165009858?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Thrush Desktop 2.1.1 Released as a Local Workbench for AI Coding

Thrush Desktop 2.1.1 has been released as a local desktop workbench for AI coding. The application combines projects, conversations, file review, and coding agents into a single desktop application.

## 🔍 Overview

Thrush features an English interface and runs either in native Windows or on Ubuntu through the Windows Subsystem for Linux (WSL). Projects and conversations are stored entirely locally. The installer includes Electron, Node, and service bundles for both Windows and Ubuntu.

## ⚙️ Key Details

Users can configure multiple model backends within the application:
*   DeepSeek
*   OpenAI
*   Anthropic-compatible gateway (requires an OpenAI-compatible gateway URL)

## 🧩 How It Works

Thrush manages changes securely by ensuring files in the original project workspace remain unchanged during a run, presenting file edits as drafts for user approval before they are applied. The workbench operates using two primary systems:

### Assist
*   Inspects files and searches code.
*   Reads web pages and runs allowlisted commands.
*   Proposes edits while restricting file tool paths to the active workspace.

### Auto
*   Requires a project with no uncommitted changes.
*   Checks the project's Git state, the Agent runtime, model configuration, and Docker availability (Docker serves as the default execution environment).
*   Creates a branch and a separate Git working copy (worktree) for each task.
*   Runs the bundled mini-swe-agent with the chosen environment and limits.
*   Collects a report, file changes, diff, logs, and execution history for review.
*   Cleans up its owned Docker containers after completion, failure, cancellation, or timeout.

Additionally, users can choose "Create Draft PR" to open a draft pull request. This action requires a GitHub origin remote and a signed-in GitHub CLI.

## 🚀 Availability

The current 2.1.1 release is for Windows 11 x64 and is positioned for internal testing. 

*   **Download**: Users can download `Thrush-2.1.1-windows-x64.exe` from the 2.1.1 release.
*   **Limitations**: The installer is unsigned. Code signing, automatic updates, and a macOS desktop release are not included.
*   **Storage**: Windows and WSL maintain separate project histories and databases. Data is stored at:
    *   Windows desktop: `%APPDATA%/Thrush/environments/native`
    *   WSL desktop: `~/.local/share/thrush/data`
    *   Source development: `data/` in the source checkout

#AICoding #Docker #Git #ThrushDesktop #AIAgents

---

*Source: [shoyann/thrush-swe-agent](https://github.com/shoyann/thrush-swe-agent)*
