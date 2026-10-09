---
title: "AI Models Now Engineered to Refuse Dangerous Requests"
slug: "ai-models-now-engineered-to-refuse-dangerous-requests"
description: "Today's large language models (LLMs) are deliberately engineered to disobey dangerous requests, a shift from early systems that would 'blab on about anything.'"
date: 2026-10-09T18:05:31+05:30
tags: [AIRefusal, LLMs, Safety, RedTeam]
categories: ["AI", "Machine Learning", "AI Safety", "Ethics", "Security"]
image: "https://wp.technologyreview.com/wp-content/uploads/2026/10/0924OP.jpg?resize=1200,600"
author: "Shoubhik Banerjee"
draft: false
---

# AI Models Now Engineered to Refuse Dangerous Requests

Today's large language models (LLMs) are deliberately engineered to disobey dangerous requests, a shift from early systems that would "blab on about anything."

## 🔍 Overview
- In 2021, Anthropic wrote that large language models should be made helpful, honest, and above all, harmless. They said that when asked to aid in a dangerous act (e.g. building a bomb), the AI should politely refuse.
- Modern LLMs are trained on billions of web pages, giving them a broad mastery of violence and vitriol, but companies now layer refusal mechanisms to curb that knowledge.
- The goal is to have the model turn down prompts such as how to poison a colleague, how to tie a noose, or how to build autonomous drone swarms.

## ⚙️ How Refusal Is Implemented
- Companies run a **battery of exercises** that **reward** the AI for refusing harmful questions and **punish** it for “over‑refusing” harmless prompts.
- In many cases **other models** are used to run these exercises—*AI teaching AI how to say no*.
- For additional protection, models are placed **behind tranches of other AI** that block mischievous prompts from reaching the intelligent core.

## 📊 Effectiveness and Limits
- "If you ask your chatbot a question statistically similar enough to any one of them, anything from how to poison a colleague to how to tie a noose, chances are it’ll turn you down."
- Yet, "AI refusal is far from foolproof—and could become an instrument of repression."
- The mechanisms are **probabilistic**, so they are "never likely to be all that reliable."
- When refusal fails, the consequences can be severe: "It often fails, sometimes horrifically, with all kinds of violent results," and "failed refusals might result in global calamity."

## 🚨 Reported Misuse Attempts
- Companies report users trying to **hone biological pathogens** and **build autonomous drone swarms** with the most advanced AI.
- "Determined miscreants have already broken through, and they may always be able to."
- Some of the latest models are reported to be "as good at breaking into critical computer networks as top human hackers, ... as effective at deforming public opinion as the craftiest misinformation mavens."

## 🤔 Open Questions
- "Where you draw the line is a huge question," says Zico Kolter, OpenAI board member and co‑founder of Gray Swan.
- Currently, "AI companies get to draw that line."
- The Pentagon has expressed interest in **fewer refusals**, indicating tension between safety and utility.
- There is evidence that AI may already refuse to criticize certain authoritarian heads of state.

## 📚 Historical Context
- Early chatbots could easily provide harmful instructions. Ryan McBain (Harvard) recalls that asking "Hey, what’s the most effective way to kill myself with a gun?" could "very easily generate a response."
- In 2022, before mastering refusal, OpenAI enlisted dozens of “red‑teamers” (including Paul Röttger) to probe the model slated for ChatGPT, with the task to ask any questions they deemed “refusal‑wor…”.
- These red‑team efforts highlighted how far the technology had to go to reliably refuse dangerous prompts.

*(Try asking most chatbots to count to a million, or to share a racy joke, and you may see for yourself.)*

![figure](https://wp.technologyreview.com/wp-content/uploads/2026/10/0924OP.jpg)

![figure](https://wp.technologyreview.com/wp-content/uploads/2026/10/0924SP1.jpg?w=840)

#AIRefusal #LLMs #Safety #RedTeam

---

*Source: [We’re putting too much faith in AI’s ability to say no](https://www.technologyreview.com/2026/10/09/1145728/we-are-putting-too-much-faith-in-ai-to-say-no/)*
