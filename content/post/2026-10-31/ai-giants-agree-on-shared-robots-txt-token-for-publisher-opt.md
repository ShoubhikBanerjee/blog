---
title: "AI giants agree on shared robots.txt token for publisher opt‑out"
slug: "ai-giants-agree-on-shared-robots-txt-token-for-publisher-optout"
description: "OpenAI, Google, Microsoft, and Anthropic announced they will adopt a new standard that lets publishers opt out of AI‑powered scraping via a shared signal placed in a site’s robots.txt file."
date: 2026-10-31T12:02:07+05:30
tags: [OpenAI, AITraining, RobotsTxt, Publishing, IETF]
categories: ["AI", "Artificial Intelligence", "Web Standards", "Content Publishing", "Machine Learning"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/chorus/uploads/chorus_asset/file/25330660/STK414_AI_CHATBOT_H.jpg?quality=90&strip=all&crop=0%2C10.732984293194%2C100%2C78.534031413613&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# AI giants agree on shared robots.txt token for publisher opt‑out

OpenAI, Google, Microsoft, and Anthropic announced they will adopt a new standard that lets publishers opt out of AI‑powered scraping via a shared signal placed in a site’s robots.txt file.

## 🔍 Overview
- The biggest names in AI are backing a new way to opt out of scraping.
- Publishers can apply their AI training preferences across multiple crawlers instead of setting them individually.
- The signal lives within the existing robots.txt file, which already tells crawlers what they may or may not scrape.

## 🧩 How it works
- A **policy token** is added to robots.txt; any AI crawler that respects the standard will read the token and honor the publisher’s preferences.
- The token was proposed by Kevin Kelley, a technical lead for standards at Anthropic, as part of the Internet Engineering Task Force (IETF) process.
- When a crawler encounters the token, OpenAI, Google, Microsoft, and Anthropic say they will restrict their AI crawlers from accessing the site.

## ⚙️ Key details
- **Meta**: Communications head Andy Stone said, “We believe creating a common signal that conveys such preferences to multiple providers at once is an important step,” and added, “And we look forward to working with other AI companies on the standards and their implementation across the industry.” Meta has signaled support but has not confirmed whether it will honor the token.
- **Microsoft**: Will offer granular controls that let publishers opt out of AI training or AI grounding. Sites will still appear in Bing search results regardless of their choices.
- **Google**: Previously implemented similar controls that let sites block AI search features or training without affecting search visibility.
- Existing efforts to curb unauthorized scraping include the Really Simple Licensing (RSL) standard, which lets publishers charge crawlers, and Cloudflare’s default blocking of AI crawlers.

## 🚀 Availability
| Company   | Current status | Planned rollout |
|-----------|----------------|-----------------|
| Anthropic | Already adopted the signal | – |
| Google    | Will support the signal | Next year |
| Microsoft | Will support the signal | Next year |
| OpenAI    | Will implement the signal | Coming months |

## 💡 Why it matters
- Publishers no longer need to negotiate separate AI training preferences with each AI provider.
- A single, standards‑based token simplifies compliance and reduces the administrative burden of managing many individual requests.
- The move comes as publishers grapple with a continuing influx of AI crawlers that feed content into large language models.
- Providing a common opt‑out mechanism could help balance the interests of content creators with the data needs of AI developers.

#OpenAI #AITraining #RobotsTxt #Publishing #IETF

---

*Source: [The biggest names in AI are backing a new way to opt out of scraping](https://www.theverge.com/tech/1023763/openai-google-microsoft-ai-scraping-standard-opt-out)*
