---
title: "AutoGen 0.2 Course Requires Model Updates After OpenAI Deprecations"
slug: "autogen-0-2-course-requires-model-updates-after-openai-deprecations"
description: "A tutorial series built on AutoGen 0.2 (pyautogen 0.2.26) is now encountering model‑not‑found errors because many OpenAI models used in the lessons have been retired."
date: 2026-11-11T22:05:42+05:30
tags: [AutoGen, OpenAI, Python, AI]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Software Development", "Python"]
image: "https://avatars.githubusercontent.com/u/71527334?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AutoGen 0.2 Course Requires Model Updates After OpenAI Deprecations

A tutorial series built on AutoGen 0.2 (pyautogen 0.2.26) is now encountering model‑not‑found errors because many OpenAI models used in the lessons have been retired.

## 🔍 Overview
- Course recorded on AutoGen 0.2; code unchanged.
- The AutoGen 0.2 line is now maintained as AG2 (pip install ag2).
- Several OpenAI models referenced in the lessons have been shut down.

## ⚙️ Key details
- Python 3.11 or 3.12 required; pyautogen 0.2.26 does not support Python 3.13.
- The pinned numpy version (1.26.4) provides wheels only up to Python 3.12.
- Lessons 01‑08, 10, 11, 13, 14 reference retired models; lessons 09 and 12 use local or Hugging Face models and are unaffected.

| Lesson | Model status |
|--------|--------------|
| 01 | Retired model |
| 02 | Retired model |
| 03 | Retired model |
| 04 | Retired model |
| 05 | Retired model |
| 06 | Retired model |
| 07 | Retired model |
| 08 | Retired model |
| 10 | Retired model |
| 11 | Retired model |
| 13 | Retired model |
| 14 | Retired model |

## 🛠️ How to adapt the course
- Change the model name in `OAI_CONFIG_LIST.json` and any \"model\": entries in `.py` files (search for `gpt-` and `dall-e`).
- Delete `temperature` and `max_tokens` from the `llm_config`; GPT‑5 models use the default temperature and `max_completion_tokens` instead of `max_tokens`.
- Use substitute models listed on the OpenAI deprecations page; for small demos `gpt-5.4-mini` costs $0.75 / $4.50 per 1 M input/output tokens (cheaper than `gpt-5.6-terra` and `gpt-5.6-sol`).
- Expect a cost‑calculation warning from pyautogen 0.2 because its price table predates the newer models.

## 📚 Additional resources
- Install requirements with `pip install -r requirements.txt`.
- Install extra Reddit project packages (`langchain-community`, `praw`) via `pip install -r 14-reddit-newsletter/requirements.txt`.
- Use PyCharm Community Edition IDE or Anaconda if preferred.
- Join the Discord community for questions.
- For the actively maintained AutoGen 0.7 API, see the TylerProgramming/ai GitHub repository.

#AutoGen #OpenAI #Python #AI

---

*Source: [tylerprogramming/autogen-beginner-course](https://github.com/tylerprogramming/autogen-beginner-course)*
