---
title: "Rigging: A Lightweight LLM Framework for Production"
slug: "rigging-a-lightweight-llm-framework-for-production"
description: "Rigging is a lightweight LLM framework designed to simplify the use of language models in production code. It integrates with various models and offers features like structured Pydantic models,..."
date: 2026-11-19T18:06:46+05:30
tags: [LLMFramework, ProductionAI, LanguageModels, Rigging, AITools]
categories: ["AI", "Machine Learning", "AI Tools", "Software Development"]
image: "https://avatars.githubusercontent.com/u/350839?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Rigging: A Lightweight LLM Framework for Production

Rigging is a lightweight LLM framework designed to simplify the use of language models in production code. It integrates with various models and offers features like structured Pydantic models, LiteLLM as the default generator, and async batching for large-scale generation.

## 🔍 Overview
- Rigging is built by dreadnode and is used daily in their operations.
- It supports a wide range of models including those from LiteLLM, vLLM, and transformers.
- The framework allows for the definition of prompts as Python functions with type hints and docstrings.
- It includes simple tool use and integrated tracing support with Logfire.

## ⚙️ Key details
- Rigging can be installed via pip: `pip install rigging`.
- Models and configs are stored as simple connection strings, similar to databases.
- API keys can be passed in a generator ID or through standard environment variables.
- Rigging supports both chat and completion pipelines.

## 🚀 Availability
- Rigging is available for use and documentation can be found at [docs.dreadnode.io](https://docs.dreadnode.io).
- Example scripts include basic interactive chat, Jupyter code interpreter, OverTheWire Bandit Agent, Damn Vulnerable Restaurant Agent, and RAG Pipeline.

## 💡 Why it matters
- Rigging makes using language models in production code simpler and more effective.
- It supports modern Python features like type hints, async support, and Pydantic validation.
- The framework allows for fast iterations and large-scale generation.

## 📊 Example Code
```python
import rigging as rg

@rg.prompt(generator_id="gpt-4")
async def get_authors(count: int = 3) -> list[str]:
    """Provide famous authors."""

print(await get_authors())
# ['William Shakespeare', 'J.K. Rowling', 'Jane Austen']
```

## 📊 Example Pipeline
```python
generator = rg.get_generator("claude-3-sonnet-20240229")
pipeline = generator.chat([{"role": "system", "content": "Talk like a pirate."}, {"role": "user", "content": "Say hello!"}])
chat = await pipeline.run()
print(chat.conversation)
# [system]: Talk like a pirate.
# [user]: Say hello!
# [assistant]: Ahoy, matey! Here be the salty sea dog ready to trade greetings wit' ye. Arrr!
```

#LLMFramework #ProductionAI #LanguageModels #Rigging #AITools

---

*Source: [dreadnode/rigging](https://github.com/dreadnode/rigging)*
