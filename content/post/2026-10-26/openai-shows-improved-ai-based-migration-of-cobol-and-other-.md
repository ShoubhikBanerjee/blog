---
title: "OpenAI Shows Improved AI‑Based Migration of COBOL and Other Legacy Code"
slug: "openai-shows-improved-aibased-migration-of-cobol-and-other-legacy-code"
description: "On October 19, OpenAI announced substantial improvements in its latest AI models’ ability to migrate aging software written in older programming languages into modern code, claiming that the advances..."
date: 2026-10-26T22:04:31+05:30
tags: [OpenAI, LegacyCode, CodeMigration, AIModels]
categories: ["AI", "Artificial Intelligence", "Software Engineering", "Legacy Systems", "Machine Learning"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/10/gettyimages-1246435991.jpg?quality=90&strip=all&crop=0%2C15.095986038394%2C100%2C69.808027923211&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI Shows Improved AI‑Based Migration of COBOL and Other Legacy Code

On October 19, OpenAI announced substantial improvements in its latest AI models’ ability to migrate aging software written in older programming languages into modern code, claiming that the advances could help organizations modernize legacy systems.

## 🔍 Overview
- OpenAI highlighted COBOL, a language created in 1959 ("common business‑oriented language"), as a primary target for migration.
- COBOL underpins critical infrastructure: more than 40 % of online banking, 80 % of in‑person credit‑card transactions, 95 % of ATM transactions, and many government systems such as Social Security, the IRS, and most state services.
- An estimate puts the annual cost of COBOL’s inefficiencies to the U.S. GDP at around $105 billion.
- Other legacy languages like Fortran remain in use for scientific computing, weather forecasting, and nuclear‑security code.

## 🛠️ How it works
- OpenAI’s blog reported successful migrations of COBOL code to modern languages including C++, Java, Kotlin, Python, and Rust **without changing what the original software does**.
- The company emphasizes that a migration is considered successful **only if all tests pass**.
- In its own tests, the model‑variant GPT‑6.1 Sol achieved 87 % behavior‑preservation accuracy at low reasoning effort, climbing to 98 % at higher reasoning effort.
- OpenAI notes that “the evaluations shown… demonstrate progress toward more accurate, affordable code migration for teams modernizing the software their businesses depend on.”

## 📊 Evaluation results
| Model | Low‑reasoning behavior preservation | High‑reasoning behavior preservation |
|-------|------------------------------------|--------------------------------------|
| GPT‑6.1 Sol | 87 % | 98 % |
| GPT‑6 Astra | ~86 % | – |
| GPT‑6 Sol | 21 % | – |
| GPT‑5.6 Sol | 5 % | – |

## 💡 Why it matters
- Migrating legacy code can reduce the massive economic drag attributed to outdated systems.
- Modern languages enable easier maintenance, security updates, and integration with current tooling.
- OpenAI also reported improvements in building database software in various languages, including COBOL.

## 🗣️ Industry reaction
- OpenAI spokesperson Oscar Haines told The Verge that legacy code “is still far from a solved problem” and that the company is listening to developer feedback and exploring better tests.
- Vadim Zaytsev, associate professor of software evolution at the University of Twente, cautioned that “rewriting code is not the same as replacing a system” and that AI currently plays a limited role in replacing or migrating large COBOL systems.
- Arie van Deursen of Delft University of Technology described OpenAI’s blog as “superficial,” noting the lack of detail about the migration task and that the benchmark used a relatively simple, well‑defined task.
- Shares in IBM, which earns revenue helping companies maintain legacy systems, nosedived after Anthropic’s announcement of its own code‑modernization playbook.
- Anthropic’s Claude Code was promoted as a way to migrate COBOL to Java or Python, but the company provided no performance benchmarks and stated only that “the economics of COBOL modernization have shifted.”

#OpenAI #LegacyCode #CodeMigration #AIModels

---

*Source: [Can AI help solve the COBOL code crisis?](https://www.theverge.com/ai-artificial-intelligence/1018434/cobol-migration-legacy-code-openai-anthropic)*
