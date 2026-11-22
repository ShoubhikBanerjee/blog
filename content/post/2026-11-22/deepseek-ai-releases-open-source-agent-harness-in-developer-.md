---
title: "DeepSeek AI releases open-source agent harness in developer preview"
slug: "deepseek-ai-releases-open-source-agent-harness-in-developer-preview"
description: "DeepSeek AI has released DeepSeek Harness (`dsh`), an open-source agent harness that is currently in developer preview."
date: 2026-11-22T22:08:30+05:30
tags: [DeepSeek, AIagents, OpenSource, DeveloperPreview, Cordis]
categories: ["AI", "AI Agents", "Open Source Software", "Developer Tools", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/148330874?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# DeepSeek AI releases open-source agent harness in developer preview

DeepSeek AI has released DeepSeek Harness (`dsh`), an open-source agent harness that is currently in developer preview.

## 🧩 How it works
DeepSeek Harness is built on an **everything-is-a-plugin** architecture. The system is powered by Cordis, a design described in the paper *A Programming Paradigm for Spatiotemporal Composability*.

## ⚙️ Key details
The project is iterating rapidly and will introduce compatibility-breaking changes. Users are advised to review the safety notice before running the project. Third-party dependencies and their licenses are disclosed in `THIRD_PARTY_NOTICES.md`.

To run the tool from a repository checkout, the following steps are required:

* `git clone https://github.com/deepseek-ai/deepseek-harness.git`
* `cd deepseek-harness`
* `pnpm install`
* `pnpm run build`
* `pnpm dsh web`

Running `pnpm run build` prepares the repository artifacts, while `pnpm dsh web` uses those built artifacts without rebuilding. For local development, `pnpm run dev:web` builds, serves, and rebuilds client bundles on source edits in a single terminal.

## 🚀 Availability
DeepSeek Harness is currently in developer preview.

* **Quick Start**: Install Node.js, then run `npx @deepseek-ai/dsh web`.
* **Web UI**: The command starts the Web UI at `http://127.0.0.1:3080` by default and opens it in the default browser.
* **SSH Launch**: Only the host URL is printed because the SSH client or editor owns the local forwarded address.
* **No Browser**: Pass `--no-open` to run the server without opening a browser.

Feedback and bug reports can be submitted through GitHub Discussions. For plugin discoverability, developers should add the `dsh-plugin` topic to their repositories.

#DeepSeek #AIagents #OpenSource #DeveloperPreview #Cordis

---

*Source: [deepseek-ai/deepseek-harness](https://github.com/deepseek-ai/deepseek-harness)*
