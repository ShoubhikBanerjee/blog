---
title: "Meta pauses Muse chat-sharing feature after security leak"
slug: "meta-pauses-muse-chat-sharing-feature-after-security-leak"
description: "Meta has temporarily disabled the Muse sharing feature that let users generate a public link to an AI conversation after researchers uncovered thousands of publicly discoverable links."
date: 2026-10-21T18:02:44+05:30
tags: [Meta, MuseAI, Privacy]
categories: ["AI", "Artificial Intelligence", "Privacy & Security", "Social Media"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/STKB394_MUSE_AI_CVIRGINIA_A.png?quality=90&strip=all&crop=0%2C9.9676601489831%2C100%2C80.064679702034&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Meta pauses Muse chat-sharing feature after security leak

Meta has temporarily disabled the Muse sharing feature that let users generate a public link to an AI conversation after researchers uncovered thousands of publicly discoverable links.

## 🔍 Overview
- Researchers at security firm Claroc reported more than 6,800 Muse links exposed through public DNS records.
- The exposure included sensitive data such as a marketing company's revenue review, a small‑business loan application, a workplace full‑year staff calendar, and interview notes for an AI‑lab candidate.
- In response, Meta paused the sharing functionality while it reviews the report.

## 🧩 How it works
- Muse allowed users to "share specific Muse artifacts, which creates a page that can be accessed by those with the link," according to spokesperson Tracy Clayton.
- Each shared page’s URL was built from the conversation’s title, a short descriptive phrase, and a random ID.
- The hostname often revealed the content type, and because the link contained the same title and ID, a hostname pulled from DNS could be used to reconstruct the full URL.

## ⚙️ Key details
- **Discovery method:** Claroc searched public DNS records, which act as a directory for web traffic, to rebuild links.
- **Volume:** Over 6,800 links were identified, with hundreds viewed by the researchers.
- **Sensitive examples:**
  - Marketing company’s revenue review
  - Small‑business owner’s loan application
  - Workplace full‑year staff calendar
  - Notes for a job candidate’s call with an AI lab
- **Meta’s response:**
  > "However, we’ve paused this functionality while we review this report and consider changes to how these links can be discovered."

## 💡 Why it matters
- The incident highlights how easily AI conversation links can become public when URL design leaks metadata.
- It joins previous cases where chat exports from OpenAI’s ChatGPT, Anthropic’s Claude, and xAI’s Grok appeared in Google Search, underscoring broader privacy challenges in AI chat sharing features.


![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/STKB394_MUSE_AI_CVIRGINIA_A.png?quality=90&strip=all&crop=0.95588235294118%2C0%2C98.088235294118%2C100&w=2400)

#Meta #MuseAI #Privacy

---

*Source: [Meta pauses Muse sharing after researchers find AI chats on the web](https://www.theverge.com/tech/1014627/meta-muse-ai-sharing-ai-chats)*
