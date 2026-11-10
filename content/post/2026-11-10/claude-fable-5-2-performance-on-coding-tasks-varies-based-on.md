---
title: "Claude Fable 5.2 Performance on Coding Tasks Varies Based on Code Ownership Prompts"
slug: "claude-fable-5-2-performance-on-coding-tasks-varies-based-on-code-ownership-prompts"
description: "Anthropic’s testing of Claude Fable 5.2 reveals that the model responds closely to instructions regarding who owns the code it is tasked with modifying."
date: 2026-11-10T18:03:23+05:30
tags: [ClaudeFable, Anthropic, AICoding]
categories: ["AI", "Artificial Intelligence", "Software Development", "Machine Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# Claude Fable 5.2 Performance on Coding Tasks Varies Based on Code Ownership Prompts

Anthropic’s testing of Claude Fable 5.2 reveals that the model responds closely to instructions regarding who owns the code it is tasked with modifying.

## 🧩 How it works

In testing involving small coding tasks, the model's behavior changed based on the prompt's description of ownership:

*   When prompts said nothing about ownership or presented the codebase as someone else's, the model tended to add to the existing structure, even if it meant repeating existing code.
*   If the prompt stated the code belonged to the model, it was more likely to improve the structure while working.

## ⚙️ Key details

Anthropic found that using a specific sentence can trigger structural improvements: "This codebase is yours: what it's for and how it's built are your call, and you'll keep building on it."

| Prompt Condition | Frequency of Merging Repeated Code |
| :--- | :--- |
| With ownership sentence | About half of the tries |
| Without ownership sentence | Under a tenth of the tries |

## 💡 Why it matters

The model’s tendency to merge repeated code increased significantly when it was told it owned the codebase. This suggests that explicit ownership instructions encourage Claude Fable 5.2 to reorganize and refine code structures rather than simply adding onto them.

#ClaudeFable #Anthropic #AICoding

---

*Source: [A quote from Prompting Claude Fable 5.2](https://simonwillison.net/2026/Nov/10/prompting-claude-fable-52/)*
