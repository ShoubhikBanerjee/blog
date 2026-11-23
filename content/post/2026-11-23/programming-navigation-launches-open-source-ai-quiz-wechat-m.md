---
title: "Programming Navigation Launches Open-Source AI Quiz WeChat Mini-Program"
slug: "programming-navigation-launches-open-source-ai-quiz-wechat-mini-program"
description: "Programming Navigation has launched a new open-source educational project: an AI quiz WeChat mini-program built on Taro, React, FastAPI, and DeepSeek. Developed by Programmer Yupi and the Programming..."
date: 2026-11-23T18:10:50+05:30
tags: [AIProgramming, WeChatMiniProgram, RAG, LangGraph, FastAPI, EducationalProject]
categories: ["AI", "AI Development", "Web Development", "Large Language Models", "Educational Technology"]
image: "https://avatars.githubusercontent.com/u/26037703?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Programming Navigation Launches Open-Source AI Quiz WeChat Mini-Program

Programming Navigation has launched a new open-source educational project: an AI quiz WeChat mini-program built on Taro, React, FastAPI, and DeepSeek. Developed by Programmer Yupi and the Programming Navigation team using Vibe Coding and OpenSpec methodologies, the project is designed to teach the full workflow of AI programming, from requirement analysis to deployment and release within the WeChat ecosystem.

## 🧩 Core Functionality
The mini-program supports three primary methods for generating quiz questions, allowing users to customize learning paths without relying on fixed question banks:
*   **One-sentence topics**: Users input a brief concept or description, and the AI generates a corresponding set of questions.
*   **Private document RAG**: Users can upload PDF, Word, Markdown, or plain text files. The backend parses, chunks, and vectorizes the text into a Chroma vector database to generate questions strictly based on the uploaded private knowledge.
*   **Web search integration**: For time-sensitive or cutting-edge topics, the system utilizes web search to ensure generated questions reflect the latest facts.

The interface supports single-choice, multiple-choice, and true/false questions. Upon submission, the system immediately highlights correct and incorrect options and provides concise explanations and knowledge point categorizations. After completing a set of questions, the system generates a personalized AI review report that includes a mastery score, a list of weak knowledge points, a three-sentence summary, and learning suggestions, along with experience points rewards.

## ⚙️ Technical Architecture
The project employs a front-end and back-end separated design:
*   **Front-end**: Built with Taro 4 and React 18, including TypeScript and Sass.
*   **Back-end**: Powered by Python 3.11+ and FastAPI, utilizing Pydantic v2 and Uvicorn.
*   **AI Orchestration**: Uses LangChain and LangGraph to manage large language models and retrieval logic. Specifically, a ReAct autonomous decision agent is built on LangGraph to determine search keywords and execution rounds for web queries.
*   **Data & Storage**: Uses MySQL with aiomysql for asynchronous connection pooling and Tencent Cloud COS for object storage.
*   **AI Services**: Integrates DeepSeek for question generation and reporting, Alibaba Cloud Bailian for embedding and text-to-image generation, and Tavily for web search.
*   **Authentication**: Implements silent login via WeChat jscode2session and JWT, while also supporting an optional login architecture that allows unregistered visitors to experience the core quiz process.
*   **Deployment**: The back-end is containerized with Docker and deployed to WeChat Cloud Hosting, completing necessary AI service category applications, ICP filings, and domain configurations.

## 💡 Educational Context
This repository serves as a hands-on teaching project for the Programming Navigation AI Quiz Learning Mini-Program course. The curriculum covers 6 major business modules and over 30 functional points, aiming to allow students to complete the full development cycle and gain resume-ready skills in less than a week. The course includes video tutorials, written notes, resume writing references, interview questions, and one-on-one Q&A services.

#AIProgramming #WeChatMini-Program #RAG #LangGraph #FastAPI #EducationalProject

---

*Source: [liyupi/yu-ai-learn](https://github.com/liyupi/yu-ai-learn)*
