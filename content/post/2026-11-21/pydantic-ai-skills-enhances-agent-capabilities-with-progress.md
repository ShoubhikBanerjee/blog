---
title: "Pydantic AI Skills Enhances Agent Capabilities with Progressive Disclosure"
slug: "pydantic-ai-skills-enhances-agent-capabilities-with-progressive-disclosure"
description: "Pydantic AI Skills introduces enhanced capabilities for Agent Skills, supporting progressive disclosure and modular packages of instructions, resources, and scripts. This update allows agents to..."
date: 2026-11-21T22:09:40+05:30
tags: [PydanticAI, AgentSkills, ProgressiveDisclosure, AIAgents, AITools]
categories: ["AI", "Machine Learning", "AI Agents", "Software Development", "AI Tools"]
image: "https://avatars.githubusercontent.com/u/8703022?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Pydantic AI Skills Enhances Agent Capabilities with Progressive Disclosure

Pydantic AI Skills introduces enhanced capabilities for Agent Skills, supporting progressive disclosure and modular packages of instructions, resources, and scripts. This update allows agents to handle specialized tasks more efficiently by loading only the necessary resources when needed.

## 🔍 Overview
- Pydantic AI Skills enhances Agent Skills with progressive disclosure.
- Supports filesystem and programmatic skills.
- Enables remote skill registries and bundled-file execution.

## 🧩 How it works
- Agent Skills are modular packages of instructions, resources, and scripts.
- On disk, a skill is a folder with a SKILL.md file, reference documents, and executable scripts.
- Your agent starts with only the name and description of each skill.
- When a task calls for a skill, it loads the full instructions and resources only if needed.
- This is progressive disclosure, allowing the skill library to grow without every skill paying for space in the prompt.

## ⚙️ Key details
- pydantic-ai-harness ships a Skills capability that reads SKILL.md packages from local directories.
- pydantic-ai-skills is the companion that fills the gaps, including remote registries and bundled-file execution.
- Remote registries support Git and S3 sources, with composition features.
- Bundled files can be read or executed with read_skill_resource and run_skill_script.
- Sandboxed execution keeps untrusted scripts off the host.
- ${SKILL_DIR} resolution substitutes the path in scripts.
- Programmatic skills can be defined in Python within the same catalog.
- v2 introduces SkillsToolset, SkillsDirectory, reload(), and tools for listing and loading skills.
- Each skill becomes its own deferred capability, with names and descriptions acting as fields the runtime uses.

## 💡 Why it matters
- Progressive disclosure allows the skill library to grow without every skill paying for space in the prompt.
- Enhanced capabilities for handling specialized tasks more efficiently.
- Supports remote skill registries and bundled-file execution.
- Sandboxed execution ensures security for untrusted scripts.


#PydanticAI #AgentSkills #ProgressiveDisclosure #AIAgents #AITools

---

*Source: [DougTrajano/pydantic-ai-skills](https://github.com/DougTrajano/pydantic-ai-skills)*
