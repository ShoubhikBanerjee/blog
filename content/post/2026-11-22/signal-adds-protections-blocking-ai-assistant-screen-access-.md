---
title: "Signal Adds Protections Blocking AI Assistant Screen Access on iOS and Android"
slug: "signal-adds-protections-blocking-ai-assistant-screen-access-on-ios-and-android"
description: "Signal has announced new protections that block screenshots on iOS 27 and prevent AI assistants from capturing conversations on supported Android devices. These measures are designed to stop built-in..."
date: 2026-11-22T22:08:30+05:30
tags: [Signal, Privacy, AIAgents, Security, iOS, Android]
categories: ["AI", "AI Agents", "Data Privacy", "Cybersecurity", "Operating Systems"]
image: "https://www.bleepstatic.com/content/hl-images/2025/09/08/Signal.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Signal Adds Protections Blocking AI Assistant Screen Access on iOS and Android

Signal has announced new protections that block screenshots on iOS 27 and prevent AI assistants from capturing conversations on supported Android devices. These measures are designed to stop built-in AI assistants, such as Siri and Gemini, from accessing private conversation content while performing tasks for users.

## 🔍 Overview
The announcement follows Signal's introduction of a feature in May 2025 that blocked Microsoft's Recall screenshot-capturing feature on Windows 11. Signal's president, Meredith Whittaker, stated that the company is now taking similar measures to restrict agentic systems built into iOS 17 and on Android versions where an AI assistant attempting to read the Signal screen can be detected.

Signal engineers spent months investigating how AI systems access app data. They designed targeted protections to block all extraction pathways, which were verified through reverse engineering. The protections specifically target OS-level features like Siri's Onscreen Awareness and Google's Gemini Intelligence, which can otherwise capture chat content as it appears on the screen. 

## ⚙️ Key Details
The new protections operate differently across platforms:

- **iOS**: The protection blocks screenshots entirely. This includes preventing users from taking screenshots of Signal conversations for legitimate purposes. On the iOS app, users can verify that "Block Siri AI" is enabled by navigating to Settings > App Security.
- **Android**: Signal automatically enables Screen Security when it detects an AI assistant attempting to access the screen. 
- **macOS**: Signal is currently unable to provide screenshot-blocking protection for macOS. For macOS 27 users, Signal recommends adding the app to the Excluded Apps list under System Settings > Siri to prevent proactive access to message content.

Signal notes that the protections are automatically activated when possible, though specific app version numbers were not provided.

## 💡 Why it Matters
Signal warns that AI agents embedded deep in operating systems pose an "existential threat" because they can access conversation data through methods beyond simple screen reading. Whittaker notes that these vulnerabilities leave apps with limited options for protecting users and expose sensitive private data belonging to all conversation participants.

In response, Signal is calling on Apple, Google, and Microsoft to provide detailed documentation disclosing all potential access mechanisms. The company urges these operating system vendors to give developers a clear way to opt out of AI access across screens, files, notifications, and APIs.

![figure](https://www.bleepstatic.com/images/news/u/1220909/2026/November/ios.jpg)

#Signal #Privacy #AIAgents #Security #iOS #Android

---

*Source: [Signal to block Siri, Gemini AI from capturing chats on iOS, Android](https://www.bleepingcomputer.com/news/security/signal-to-block-siri-gemini-ai-from-capturing-chats-on-ios-android/)*
