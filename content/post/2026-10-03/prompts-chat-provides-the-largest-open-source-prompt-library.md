---
title: "Prompts.chat provides the largest open-source prompt library for modern AI assistants"
slug: "prompts-chat-provides-the-largest-open-source-prompt-library-for-modern-ai-assistants"
description: "Prompts.chat, formerly known as Awesome ChatGPT Prompts, is an open-source platform that allows users to share, discover, and collect prompts for AI chat models. Established in December 2022 as the..."
date: 2026-10-03T22:03:57+05:30
tags: [PromptEngineering, OpenSource, AIModels, WebDevelopment]
categories: ["AI", "Generative AI", "Software Development", "EdTech"]
image: "https://avatars.githubusercontent.com/u/196477?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Prompts.chat provides the largest open-source prompt library for modern AI assistants

Prompts.chat, formerly known as Awesome ChatGPT Prompts, is an open-source platform that allows users to share, discover, and collect prompts for AI chat models. Established in December 2022 as the first prompt library, it is free, open-source, and can be self-hosted by organizations wanting complete privacy.

## 🔍 Overview

Originally built for ChatGPT, the prompts in this library now work with modern AI assistants including Claude, Gemini, Llama, and Mistral. The platform has achieved notable academic and community recognition:
* It is the most liked dataset on Hugging Face.
* It has earned over 143,000 GitHub stars and is a GitHub Staff Pick.
* It was featured in Forbes and referenced by Harvard and Columbia.
* It has accumulated more than 40 academic citations.

## 🧩 Features and Capabilities

* **Community Submissions**: Users can submit new prompts at `prompts.chat/prompts/new`, which sync automatically to the platform.
* **Interactive Learning Guide**: A free guide with 28+ chapters covers prompt engineering topics ranging from foundational basics to advanced techniques like chain-of-thought reasoning, few-shot learning, and AI agents.
* **Educational Adventure**: A game-based interactive experience teaches children ages 8 to 14 how to communicate with AI using stories and puzzles.
* **Private Deployment**: Organizations can launch a self-hosted prompt library with custom branding, custom themes, and authentication.

## ⚙️ Deployment and Setup

Users can initialize and customize their own private prompt library. The setup wizard configures branding, themes, features, and authentication options (including GitHub, Google, and Azure AD). Prompts.chat utilizes PostgreSQL for data storage, with Neon recommended for hosted database services.

To start a new project, use:
```bash
npx prompts.chat new my-prompt-library
```

To set up the library manually, run:
```bash
git clone https://github.com/f/prompts.chat.git
npm install && npm run setup
```

You can also launch it using:
```bash
npx prompts.chat
```

#PromptEngineering #OpenSource #AIModels #WebDevelopment

---

*Source: [f/prompts.chat](https://github.com/f/prompts.chat)*
