---
title: "Llamatik 2.0: Kotlin Multiplatform AI SDK with Agent Framework"
slug: "llamatik-2-0-kotlin-multiplatform-ai-sdk-with-agent-framework"
description: "Llamatik 2.0 is a major architectural release of the Kotlin Multiplatform AI SDK, extracting reusable business logic into a clean, UI-agnostic, publishable SDK. It introduces a full Agent Framework..."
date: 2026-11-21T22:09:40+05:30
tags: [Kotlin, AI, AgentFramework, Multiplatform, Llamatik]
categories: ["AI", "Machine Learning", "AI Agents", "Software Development", "Kotlin"]
image: "https://avatars.githubusercontent.com/u/287465123?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Llamatik 2.0: Kotlin Multiplatform AI SDK with Agent Framework

Llamatik 2.0 is a major architectural release of the Kotlin Multiplatform AI SDK, extracting reusable business logic into a clean, UI-agnostic, publishable SDK. It introduces a full Agent Framework for building agentic AI applications in Kotlin.

## 🔍 Overview
- Llamatik is a 2026 Kotlin Foundation Grant winner.
- It provides a true on-device AI SDK for Kotlin Multiplatform (Android, iOS, Desktop, JVM, WASM).
- The SDK includes LLM inference, Speech-to-Text, Image Generation, Agent Framework, and RAG — powered by llama.cpp, whisper.cpp, and stable-diffusion.cpp.
- Run AI locally on Android, iOS, Desktop, and WASM — using a single Kotlin API.

## 🧩 How it works
- The inference library is now published as com.llamatik:core.
- All existing APIs — LlamaBridge, WhisperBridge, StableDiffusionBridge, MultimodalBridge — are unchanged.
- Business logic has been extracted from the application layer into a new :sdk module with zero UI or Compose dependencies — making it directly publishable and usable in any Kotlin Multiplatform project.
- A new Assistant class (com.llamatik.sdk.assistant) owns all inference orchestration — chat, RAG, image generation, VLM, STT, model download, and session persistence — in a single, injectable facade.

## ⚙️ Key details
- A complete Kotlin DSL for building agentic AI applications: Agent { } DSL — declarative agent creation with name, system prompt, temperature, memory, and tools.
- Memory options include ConversationMemory, SlidingWindowMemory(windowSize), PersistentMemory, and SummaryMemory.
- Tool Support — built-in tools (Calculator, DateTime, UUID, Random) + custom tool registration.
- Streaming — agent.stream() returns a Flow<AgentStreamChunk> for token-by-token output.
- Workflows — sequential Step execution with WorkflowContext, approval gates, and continueOnError().
- Observable Events — agent.events: SharedFlow<AgentEvent> for turn lifecycle hooks.
- A production-ready agentic runtime for host-app integration: AgentRuntime — LLM-backed planner + execution engine with permission → confirmation → action → audit pipeline.
- Permission Management — PermissionManager, KnownPermissions, grant/deny/ask-every-time policies.
- 9 Built-in Platform Tools — Calendar, Reminder, OpenApp, OpenUrl, Clipboard, Share, Notification, SearchContacts, OpenSettings.
- Companion Profiles — Assistant, Professional, Friendly, Companion, Pet personas with configurable style and planning aggression.
- Persistent Memory — AgentMemory (Settings-backed, tag + type search, 200 entries).
- Audit Log — AgentAuditRepository (Settings-backed, 1000 entries cap).
- Workflow Engine — AgentWorkflowEngine (Flow-based, conditional/retry, WorkflowRepository).

## 🚀 Availability
- Llamatik 2.0 is a major architectural release that extracts all reusable business logic into a clean, UI-agnostic, publishable SDK — and adds a full Agent Framework for building agentic AI applications in Kotlin.

## 💡 Why it matters
- Llamatik is a Kotlin Multiplatform AI SDK that covers the full stack — from low-level on-device inference to high-level agent orchestration.

#Kotlin #AI #AgentFramework #Multiplatform #Llamatik

---

*Source: [llamatik/Llamatik](https://github.com/llamatik/Llamatik)*
