---
title: "Hodor: An Agentic LLM‑Powered Code Reviewer for Git Repositories"
slug: "hodor-an-agentic-llmpowered-code-reviewer-for-git-repositories"
description: "A new AI tool called Hodor provides an agentic code reviewer that can be run on GitHub pull requests, GitLab merge requests, Gitea/Forgejo pull requests, and local diffs."
date: 2026-11-01T06:02:40+05:30
tags: [AI, CodeReview, DevOps, LLM]
categories: ["AI", "Artificial Intelligence", "Developer Tools", "Machine Learning", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/5689132?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Hodor: An Agentic LLM‑Powered Code Reviewer for Git Repositories

A new AI tool called Hodor provides an agentic code reviewer that can be run on GitHub pull requests, GitLab merge requests, Gitea/Forgejo pull requests, and local diffs.

## 🔍 Overview
- Reviews code changes by invoking an LLM agent with confined inspection tools (`git_diff`, `read`, `grep`, `find`, `ls`).
- Returns structured findings as inline comments and a summary note, or prints them locally.
- Supports a default review protocol that remains unchanged unless explicitly overridden.

## 🧩 How it works
1. Hodor checks out the change and automatically resolves to the git repository root, even when invoked from a subdirectory.
2. It supplies the LLM with the limited toolset listed above and asks for a structured review.
3. Findings are posted as inline comments and a summary, or output to the console.
4. Optional instruction files can be added; they are additive, repeatable, and later files win conflicts, while `--focus` instructions win over file‑based instructions.
5. The `--profile security` flag prefixes the bundled security‑review instructions before any explicit instruction files, narrowing reporting to security vulnerabilities without replacing the baseline protocol.

## ⚙️ Key details
- **Included changes**: uncommitted (staged + unstaged) changes, not only committed code.
- **Repository handling**: skips PR metadata fetching and workspace cloning.
- **Default model**: `anthropic/claude-opus-5-5`.
- **Reasoning effort**: Adaptive.
- **Optional flags**:
  - `--ultrathink` – Off
  - `--full` – Off
  - `--post` – disabled (no remote posting)
  - `--target-branch` – None
- **Supported LLM providers**: Anthropic, OpenAI, Bedrock, OpenRouter; other providers are best‑effort.

| Flag / Option                | Default / State | Description                                               |
|------------------------------|-----------------|-----------------------------------------------------------|
| `--model`                    | `anthropic/claude-opus-5-5` | Base LLM used for the review |
| `--reasoning-effort`         | Adaptive        | Level of reasoning effort applied |
| `--ultrathink`               | Off             | Extended reasoning mode (disabled) |
| `--full`                     | Off             | Full‑snapshot review mode (disabled) |
| `--post`                     | Disabled        | Remote posting of comments (disabled) |
| `--target-branch`            | None            | Branch to compare against (none by default) |

## 🚀 Availability
- Docker images are published at `ghcr.io/mr-karan/hodor:<version>` for use in CI pipelines.
- Pinning a version in CI keeps reviews comparable across runs.
- When installed globally via `npm install -g`, the command `npx @mrkaran/hodor` can be replaced with `hodor`.

## 💡 Why it matters
- Enables consistent, automated code reviews across multiple Git platforms without requiring repository cloning.
- Allows security‑focused reviews via `--profile security` or `--focus "Report only security findings."` while preserving baseline defect checks.
- Supports a range of LLM back‑ends, making it adaptable to existing infrastructure.
- Works on local, uncommitted changes, helping developers catch issues before committing.


#AI #CodeReview #DevOps #LLM

---

*Source: [mr-karan/hodor](https://github.com/mr-karan/hodor)*
