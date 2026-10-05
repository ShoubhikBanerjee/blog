---
title: "Open‑Source RemoveMacAI Tool Deletes Apple Intelligence Models, Frees Up Storage"
slug: "opensource-removemacai-tool-deletes-apple-intelligence-models-frees-up-storage"
description: "A new open‑source command‑line utility called **RemoveMacAI** lets macOS users delete Apple Intelligence models and disable its bundled AI features in a single step, reclaiming roughly a dozen..."
date: 2026-10-05T22:07:36+05:30
tags: [AppleIntelligence, macOS, OpenSource, CLI]
categories: ["AI", "Operating Systems", "Artificial Intelligence", "Open Source Software", "Storage Management"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/06/highlights_siri_conversations_endframe__d56qnw2oz22q_large_2x.jpg?quality=90&strip=all&crop=17.168746500778%2C34.087860369258%2C65.996740905563%2C64.026266887145&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Open‑Source RemoveMacAI Tool Deletes Apple Intelligence Models, Frees Up Storage

A new open‑source command‑line utility called **RemoveMacAI** lets macOS users delete Apple Intelligence models and disable its bundled AI features in a single step, reclaiming roughly a dozen gigabytes of disk space.

## 🔧 What RemoveMacAI Does
- ‘RemoveMacAI’ **switches off Apple’s AI features**, deletes its AI models, and blocks them from being downloaded again.
- It removes the on‑disk foundation models, which the developer says take up **about 12 GB** of space (some users report even more).
- The changes **persist across macOS updates**.
- **Dictation** continues to work after removal.
- The tool provides a **`removemacai revert`** command to re‑enable all features and allow the models to download again.
- A **`removemacai status`** command shows the size of each individual AI model on the Mac.

> “I wrote RemoveMacAI to do all of it in one go.”

## 📦 Storage Impact
- Apple Intelligence models remain on disk by default, occupying **about 12 GB** according to the developer.
- A user measured **35.05 GB** of space labeled “Apple Intelligence” on a MacBook Air.
- Running RemoveMacAI deletes these models, freeing the corresponding storage.

## ⚙️ How It Works
1. The tool toggles off the following AI‑related features:
   - Siri
   - Writing Tools
   - Genmoji
   - Image Playground
   - The ChatGPT extension
   - All summary functions
2. It then deletes the stored foundation models from the file system.
3. Finally, it prevents macOS from re‑downloading the models unless the user runs `removemacai revert`.

## 📋 Feature List
| Feature            | Action performed by RemoveMacAI |
|--------------------|-----------------------------------|
| Siri               | Turned off                        |
| Writing Tools      | Turned off                        |
| Genmoji            | Turned off                        |
| Image Playground   | Turned off                        |
| ChatGPT extension  | Turned off                        |
| Summaries          | Turned off                        |

## 📆 Availability
- The utility is **open‑source** and was announced by its developer on **Reddit**.
- It replaces the single Settings toggle that existed for disabling Apple Intelligence before it was removed in **macOS 27**, where the models stayed on disk and settings were split across multiple panes (including several under Screen Time).

## 💡 Why It Matters
- Users who prefer not to run Apple’s on‑device AI can now remove the models entirely, reclaiming storage without losing core functionality like Dictation.
- The tool simplifies what previously required navigating **about a dozen settings** across various preference panes.
- By blocking future downloads, it ensures the storage savings remain until the user decides to restore the features.


![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/06/highlights_siri_conversations_endframe__d56qnw2oz22q_large_2x.jpg?quality=90&strip=all&crop=20.329205691131%2C34.122126453008%2C53.328795281996%2C65.877873546992&w=2400)

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/10/chatgpt-visual-ads.webp?quality=90&strip=all&crop=12.5%2C0%2C75%2C100&w=2400)

#AppleIntelligence #macOS #OpenSource #CLI

---

*Source: [An open-source tool lets you delete 12GB of Apple Intelligence data on macOS](https://www.theverge.com/ai-artificial-intelligence/1004672/mac-delete-apple-intelligence-ai-tool)*
