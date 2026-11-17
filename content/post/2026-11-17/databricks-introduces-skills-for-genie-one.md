---
title: "Databricks introduces Skills for Genie One"
slug: "databricks-introduces-skills-for-genie-one"
description: "Databricks has introduced a new feature for Genie One called Skills, which adds a layer of control by defining specific workflow recipes that the agent can follow on demand to ensure consistent..."
date: 2026-11-17T18:10:30+05:30
tags: [Databricks, GenieOne, AISkills, MCP, WorkflowAutomation]
categories: ["AI", "AI Agents", "Generative AI", "Data Analytics", "Workflow Automation"]
image: "https://www.databricks.com/sites/default/files/2026-11/2026-10-Blog-Teach-Genie-One-your-workflows-The-ultimate-guide-for-skills-in-Genie-One-OG-1200x628-2x.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks introduces Skills for Genie One

Databricks has introduced a new feature for Genie One called Skills, which adds a layer of control by defining specific workflow recipes that the agent can follow on demand to ensure consistent formats and outputs.

## 🧩 How it works
A skill is a durable, reusable asset that serves as a written record of how a team works, using plain language and the open Agent Skills format. Genie One leverages skills either when called directly by the user or when it decides a skill is relevant to the request. 

*   **Scope and Isolation**: Guidance stays with the specific task rather than spilling into other work. Because Genie One only reads the skills it needs, keeping them specific and focused is advantageous for testing, fixing, and reusing them.
*   **Chainable Assets**: Small skills can be chained together; for example, updating a style guidelines skill once allows every other skill that uses it to pick up the change.
*   **Judgment vs. Routines**: While dashboards do the same thing every time, skills allow Genie One to make decisions, such as choosing the most important changes for leadership or following unusual results until they make sense.
*   **Strict Rules**: Skills define what must always appear, what to do when something is missing, and thresholds that decide what gets a closer look. For instance, a trading brief might always include a watch list even if nothing breached a threshold.

## ⚙️ Key details
Skills distinguish themselves from Genie Agents and Genie Ontology by focusing on the method rather than domain knowledge:

| Component | Function |
| :--- | :--- |
| **Genie Ontology** | Tells Genie One what things mean. |
| **Genie Agent** | Domain expert for one area (e.g., sales, finance, HR); knows metric definitions, tables, joins, and business rules. |
| **Skill** | Recipe for a specific task: the steps, checklist, and output format. |

For example, a sales pipeline Genie Agent knows the pipeline tables and stage definitions, while a "weekly forecast risk memo" skill instructs Genie One to compare current and previous pipeline data, flag slipped deals, and produce a one-page memo. The Genie Agent supplies domain knowledge, and the skill supplies the workflow.

## 💡 Why it matters
You can build a skill directly in Genie One by explaining your workflow in detail once, prompting the agent to interview you before writing the skill. Genie One draws on existing knowledge through Genie Ontology to focus questions on how you work rather than what your data means. Answering in plain language is enough for Genie One to write the skill. Once built, a skill can be published through Unity Gateway and used by any agent that supports MCP, including coding agents teams already use.

Consider using a skill when you find yourself explaining the same thing to Genie One more than once.

![figure](https://www.databricks.com/sites/default/files/blog_images/teach-genie-one-your-workflows-the-ultimate-blog-img-og.png)

#Databricks #GenieOne #AISkills #MCP #WorkflowAutomation

---

*Source: [Teach Genie One your workflows: The ultimate guide for skills in Genie One](https://www.databricks.com/blog/teach-genie-one-your-workflows-ultimate-guide-skills-genie-one)*
