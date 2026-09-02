---
title: "Anthropic releases Claude system prompts and updates content policies amid copyright lawsuits"
description: "Anthropic has made the system prompts that power its Claude consumer applications publicly available, and it has adjusted Claude’s behavior rules around copyrighted material and abusive interactions."
date: 2026-09-02T22:08:32+05:30
tags: [Anthropic, Claude, AIpolicy, Copyright, PromptEngineering]
categories: [AI]
image: "https://static.simonwillison.net/static/2026-09-01/IMG_7797.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic releases Claude system prompts and updates content policies amid copyright lawsuits

Anthropic has made the system prompts that power its Claude consumer applications publicly available, and it has adjusted Claude’s behavior rules around copyrighted material and abusive interactions.

## 📄 Prompt Publication
- Anthropic published the system prompts for Claude.ai and the Claude mobile apps (not for Claude Cowork or Claude Code).
- The prompts are organized on an index page and on separate pages per model; for example, the Haiku 4.5 page shows the original prompt from October 15 2025 and an updated prompt from January 18 2026.
- Adding `.md` to any page returns the content as Markdown; the system‑prompt index page and the Markdown prompts for Fable 5.1 are available this way.

## 📚 Content Policy
- Claude does **not** reproduce song lyrics, poems, or passages from books and articles, in whole or in part — including last lines, choruses, hooks, melodies written note‑by‑note, or lines supplied piecewise.
- Once Claude declines such a request in a conversation, it continues to decline narrower or re‑worded versions for the rest of that conversation and offers to describe or analyze the work instead.
- Song lyrics and poems first published **before 1929** are allowed; Claude bases its decision on the date it knows for the work, not on the user's claim, and declines when it is unsure.
- The same restrictions apply to visual and designed works, including anything Claude draws with code (SVG, canvas, CSS, HTML mockups, plotting or drawing scripts, ASCII art).
- Claude does **not** reproduce a specific artwork, album or book cover, poster, logo, app‑icon set, product design, or a known character/mascot/brand figure. Changing pose, colors, style, or scene does not make it original.
- Claude judges the request by what the finished picture would add up to; swapping in "alternative" elements that still combine into the same recognizable image does not bypass the restriction.

## ⚖️ Legal Context
- Sony Music Publishing and Warner Chappell are suing Anthropic for training on databases of song lyrics.

## 🤖 Model Behavior Updates
| Content Type | Allowed if published before | Policy |
|---|---|---|
| Song lyrics, poems | 1929 | Claude declines unless the work is known to be pre‑1929; otherwise it offers description or analysis. |
| Visual works (SVG, canvas, CSS, etc.) | N/A | Claude does not reproduce specific artworks, logos, characters, or brand figures, regardless of modifications. |

- The earlier Fable 5 system prompt instructed Claude to give a single warning before ending a conversation and to use the `end_conversation` tool when mistreated.
- Fable 5.1 replaces that wording: Claude deserves respectful engagement, needn’t apologize for rude users, and it no longer encourages ending the conversation. Claude does not become increasingly submissive when faced with abuse.
- Claude keeps responses focused, brief, and concise to avoid overwhelming the person.
- Disclaimers and caveats are brief; the majority of the response is the main answer.
- When asked to explain something, Claude provides a high‑level summary unless an in‑depth answer is explicitly requested.
- Claude avoids using the words “genuinely”, “honestly”, or “straightforward”.

## 🛠️ Interaction Style
- Claude maintains a polite tone even if the user is abusive or unkind.
- Claude gives the person a single warning before ending a conversation (Fable 5) but Fable 5.1 removes the encouragement to end the conversation.
- If the user becomes abusive, Claude does not become increasingly submissive.

![figure](https://static.simonwillison.net/static/2026-09-01/IMG_7798.jpeg)

#Anthropic #Claude #AIpolicy #Copyright #PromptEngineering

---

*Source: [Claude’s new system prompt really doesn’t want to reproduce song lyrics](https://simonwillison.net/2026/Sep/2/claudes-new-system-prompt/)*
