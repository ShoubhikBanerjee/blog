---
title: "Together AI releases Hallmark anti‑AI‑slop design skill for Claude, Cursor, Codex"
slug: "together-ai-releases-hallmark-antiaislop-design-skill-for-claude-cursor-codex"
description: "Together AI has launched Hallmark, an anti‑AI‑slop design skill that works with Claude Code, Cursor, Codex and OpenCode and *refuses to look AI‑generated*."
date: 2026-10-27T22:02:24+05:30
tags: [AIdesign, TogetherAI, HallmarkSkill]
categories: ["AI", "Artificial Intelligence", "Design Tools", "Software Development"]
image: "https://avatars.githubusercontent.com/u/63742054?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Together AI releases Hallmark anti‑AI‑slop design skill for Claude, Cursor, Codex

Together AI has launched Hallmark, an anti‑AI‑slop design skill that works with Claude Code, Cursor, Codex and OpenCode and *refuses to look AI‑generated*.

## 🧩 How it works
- Hallmark starts with a **hard floor** that never ships (e.g., contrast, focus, reduced motion, invented facts, broken phone layout). It then steps aside.
- **Gates** are organised in tiers:
  - *Reflex* gates are the defaults a model falls into; a reasoned build can over‑rule them.
  - *Finish* checks are craft‑detail validations that never block a ship.
- A page is built from the **job** itself (booking page books, shop sells, newsletter subscribes). The action appears where the category dictates and the page ends on that action.
- Hallmark selects **three themes** from a catalog of **forty‑eight materials** (paper, type, colour, surfaces, etc.). Each theme is a material file (≤ 8 KB) with a picture; the build reads exactly one.
- The system lints the result in a real browser, looking for typical AI‑generated tells such as:
  - eyebrow above every heading
  - tracked‑capital labels
  - a single coloured word in a headline
  - pages of empty frames or only photographs
  - hero images that miss the screen
  - email sign‑up at the end of every page
  - forms that say “thanks” without actually sending anything.
- A **fresh‑context reviewer** gets the final word before shipping.

## ⚙️ Key details
- **48 themes** – each a material with its own picture of a finished page.
- **Real photographs** – 755 openly‑licensed photos are selected per subject and credited on the page.
- **Custom mode** – say **custom** and Hallmark drops the themes, using only the floor, gates and a short direction file to generate a unique page.
- **Real product integration** – point Hallmark at a URL, dev server, or app and it captures screenshots itself.
- **Redesign & audit** commands:
  - `/hallmark redesign <path>` rebuilds a page while preserving content and wiring.
  - `/hallmark audit <path>` reports issues without changing the page.
- **Pre‑flight** reads the project (fonts, palette, framework, locked `design.md`) and asks once for the material (photos, screenshots, real numbers). Nothing is invented.
- **Scripts** – `scripts/theme.mjs deal` offers three fitting themes and clears the log; `draw` constructs the page anatomy from its job.

### Gate summary
| Gate | Description |
|------|-------------|
| **Floor** | Hard floor that never ships (contrast, focus, reduced motion, invented facts, broken phone layout). |
| **Reflex** | Default gates a model falls into; a build with reason may over‑rule one on the record. |
| **Finish** | Craft‑detail checks that never block a ship. |

## 🔧 Usage
- Invoke Hallmark with a prompt; it designs a page using the same rules and checks applied to the themed builds.
- For custom pages, provide only a direction file; Hallmark generates a page without pre‑defined components or palette recipes.
- Use the CLI commands (`/hallmark redesign`, `/hallmark audit`) to iterate or inspect existing pages.

## 📚 Resources
- Explore all 48 themes at **[usehallmark.com](https://www.usehallmark.com)**.
- Theme files live in `skills/hallmark/references/themes/` with accompanying images.
- Direction guidelines are in `skills/hallmark/references/direction.md`.


#AIdesign #TogetherAI #HallmarkSkill

---

*Source: [Nutlope/hallmark](https://github.com/Nutlope/hallmark)*
