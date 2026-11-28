---
title: "AI Study Tool Parses Courses and Tracks Skill Mastery Maps"
slug: "ai-study-tool-parses-courses-and-tracks-skill-mastery-maps"
description: "An AI development tool has been released that allows users to upload various study materials, including lectures, web pages, screenshots, recordings, and Bilibili courses. The system automatically..."
date: 2026-11-28T22:07:57+05:30
tags: [AI, StudyTools, MacOS, Whisper, SkillMastery]
categories: ["AI", "AI Development", "Productivity Tools", "Education Technology"]
image: "https://avatars.githubusercontent.com/u/39698639?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AI Study Tool Parses Courses and Tracks Skill Mastery Maps

## 🔍 Overview
An AI development tool has been released that allows users to upload various study materials, including lectures, web pages, screenshots, recordings, and Bilibili courses. The system automatically parses these inputs into searchable knowledge bases. It supports PDF, DOCX, TXT, Markdown, web pages, images, audio, and Bilibili/YouTube videos, requiring macOS, Python 3.12, uv, Node 20+, and ffmpeg.

## 🧩 How it works
The system processes different data types using specific methods:
*   **Documents:** Split by title hierarchy, preserving "Material > Chapter > Section" structure. PDFs are processed to remove duplicate headers, footers, and page numbers.
*   **Web Pages:** Prioritize the DeepSeek scraping interface, falling back to local parsing if it fails.
*   **Images:** Use macOS Vision to recognize Chinese text; if unrecognized, it attempts DeepSeek OCR.
*   **Videos:** Search for subtitles first. If missing, it uses local Whisper for transcription, extracts frames, performs OCR, and aligns explanations to pages to generate notes with timestamps and keyframes.
*   **Ingestion:** Recognized in batches of 20 pages. A failure in one batch does not affect others, and truncated pages are marked in the output.

From the materials, the tool extracts how knowledge points are tested, question formats, steps, pitfalls, and variations. If materials contain questions, they are automatically moved to the question bank and tagged with fine-grained labels. For example, specific topics like the "Cow Eating Grass" problem type are used for tagged question selection during exam generation.

## 📊 Skill Mastery and Practice
The tool generates exams by module with time limits, automatically grades them, and explains error reasons while updating mastery levels. A skill map displays the practice level of each section, with statuses including Proficient, Can Use, Understands, Unclear, and Needs Review. Weekly plans and reports are based on actual answering data rather than model fabrication.

*   **Question Selection:** Exams are grouped by subject, module, difficulty, and quantity. A default 30-question set includes 28 single-choice and 2 short-answer questions.
*   **Answering Interface:** Includes a countdown, answer sheet, and auto-save. When time expires, the paper is submitted automatically.
*   **Reporting:** Provides per-question analysis, scoring rubric hits, corresponding skills, mastery changes, and variation problems for practice.

## ⚙️ Key Details
*   **Default System:** Uses the "Peanut 13" system, categorizing materials into 8 major blocks (Material Analysis, Quantitative Relations, Verbal Understanding, Judgment Reasoning, Common Sense Judgment, Essay, Answering Strategy, Exam Planning) with over 200 skills.
*   **Cost Tracking:** Records invocation volume and costs for each model and provider. DeepSeek is calculated at official website prices (including peak/idle periods), while local Ollama is recorded as free.
*   **No Key Mode:** The workflow can be completed without an API key. Demo mode returns fixed academic, exam, and knowledge base answers. Document ingestion uses local hash vectors, requiring no Embedding Key.

## 📱 Availability and Requirements
*   **iOS App:** Built with native SwiftUI, minimum requirement iOS 17. Supports using Apple Pencil on a scratchpad for handwritten calculations during exams, saving one page per question for review after submission.
*   **MacOS Requirements:** Necessary for image OCR and iOS integration, though the backend is cross-platform.
*   **Development Program:** The 99 USD/year Developer Program only affects App Store listing and TestFlight distribution; it is not required for self-installing on devices.
*   **Signing Limitations:** Signatures expire after 7 days, requiring reconnection to a Mac to run. Supports a maximum of 3 devices with only 10 App IDs active at the same time.

#AI #StudyTools #MacOS #Whisper #SkillMastery

---

*Source: [yijiejiang/kaogong-school](https://github.com/yijiejiang/kaogong-school)*
