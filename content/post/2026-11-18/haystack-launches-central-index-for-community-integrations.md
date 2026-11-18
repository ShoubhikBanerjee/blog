---
title: "Haystack Launches Central Index for Community Integrations"
slug: "haystack-launches-central-index-for-community-integrations"
description: "A new repository provides an index of Haystack integrations that can be used with a Haystack Pipeline or Agent."
date: 2026-11-18T22:09:17+05:30
tags: [Haystack, Integrations, OpenSource, MachineLearning]
categories: ["AI", "Machine Learning", "Open Source", "Software Development"]
image: "https://avatars.githubusercontent.com/u/51827949?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Haystack Launches Central Index for Community Integrations

A new repository provides an index of Haystack integrations that can be used with a Haystack Pipeline or Agent.

## 📂 Overview
This repository lists integrations that are maintained by their respective owners or authors and can be browsed on the Haystack Integrations page.

## 🛠️ Types of Integrations
- Document Store
- Model Provider
- Data Ingestion
- Monitoring Tool
- Evaluation Framework
- Custom Component
- Tool Integration
- Something new!

## 📄 Contribution Guide
- Create a pull request adding a `.md` file to the `integrations/` directory.
- Start with the draft integration page: https://github.com/deepset-ai/haystack-integrations/blob/main/draft-integration.md
- Include required frontmatter fields (see table).
- Ensure at least one of `pypi` or `repo` fields is present.
- After merging, the integration will appear on the integrations page.

## 🗂️ Frontmatter Fields
| Field | Requirement |
|---|---|
| layout | required |
| name | required |
| description | required |
| authors | required (name of each author) |
| type | required |
| toc | optional |
| logo | optional |
| version | required (Haystack 2.0) |
| pypi | optional (must include if no `repo`) |
| repo | optional (must include if no `pypi`) |
| report_issue | optional |

## 🚀 Availability
Browse all integrations on the Haystack Integrations page (https://haystack.deepset.ai/integrations) to see author information, installation instructions, and usage details.


#Haystack #Integrations #OpenSource #MachineLearning

---

*Source: [deepset-ai/haystack-integrations](https://github.com/deepset-ai/haystack-integrations)*
