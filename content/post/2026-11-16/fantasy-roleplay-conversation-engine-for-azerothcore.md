---
title: "Fantasy Roleplay Conversation Engine for AzerothCore"
slug: "fantasy-roleplay-conversation-engine-for-azerothcore"
description: "A fantasy roleplay conversation engine for AzerothCore WotLK (3.3.5a) and mod-playerbots."
date: 2026-11-16T22:14:27+05:30
tags: [AI, MMO, Roleplay, Chatbot]
categories: ["AI", "Artificial Intelligence", "MMORPG", "Game Development", "Chat Automation"]
image: "https://avatars.githubusercontent.com/u/14316162?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Fantasy Roleplay Conversation Engine for AzerothCore

A fantasy roleplay conversation engine for AzerothCore WotLK (3.3.5a) and mod-playerbots.

## 🔍 Overview
- Replaces the silence of automated bots with personality-driven, lore-grounded dialogue.
- Gives every companion a voice shaped by their race, class, and the surrounding world.
- Built from the ground up for fantasy roleplay immersion.
- Bots speak as distinct inhabitants of Azeroth, not as AI assistants breaking the fourth wall.

## 🧩 How it works
- A lightweight WoW addon lets you view and edit bots' personality traits, tone, and background story via the game UI.
- Open with /chatter or /llmc, pick a bot, tweak personality, read or regenerate its origin story.
- Changes are reflected immediately, with no server restart required.
- LLM processing runs in a separate concurrent bridge service.
- Worldserver queues events and delivers responses without waiting on provider calls.
- The module is cloned into modules/ and built with AzerothCore.
- Configuration requires copying conf/mod_llm_chatter.conf.dist to your config directory and setting LLMChatter.Provider, LLMChatter.Model, and API key (Ollama does not need a key).
- Start worldserver once or run dbimport to apply the module's character database schema, then start the Python bridge.
- Play, and bots start chatting when grouped with players.

## ⚙️ Key details
- More than 3,000 zone and subzone descriptions ground dialogue in lore.
- Bots notice nearby creatures, NPCs, objects, points of interest, weather, time, transports, and holidays.
- Companions banter, ask questions, and react to combat, loot, quests, achievements, travel, ambushes, kills, deaths, ganks, duels, and PvP kills.
- Same-faction onlookers comment in /say; opposite-faction onlookers emote, with reactions restrained by low chances and shared cooldowns, and hidden enemy identities omitted.
- Ambient General chat, proximity /say, player replies, battleground callouts, and encounter-aware raid dialogue populate the world.
- Guildmates greet returning players, answer messages, hold conversations, and carry shared context forward.
- Mail arrives after dungeons, raids, or key quests from remembering bots or trainers with gifts.
- Friendly NPCs discuss actions in the regions where they occurred.
- Each companion maintains a stable identity, generated backstory, and memories of shared dungeons, bosses, achievements, and milestones.
- Backstories can be viewed or regenerated through the Chatter Companion addon.
- Bots size up enemies by name, race, class, and level, reacting in character to ambushes, kills, deaths, and ganks.

## 🚀 Availability
- Requires a working AzerothCore server with mod-playerbots.
- Installation guide includes Docker install for AzerothCore, the Playerbot branch, and mod-playerbots.
- Clone the module into modules/ and build AzerothCore.
- Copy conf/mod_llm_chatter.conf.dist to your config directory and name it mod_llm_chatter.conf.
- Set LLMChatter.Provider, LLMChatter.Model, and the matching API key (Ollama does not need a key).
- Start worldserver once, or run dbimport so AzerothCore applies the module's character database schema.
- Start the Python bridge.
- Keep upstream dependencies up to date, especially both AzerothCore's Playerbot branch and mod-playerbots.
- Older versions may no longer compile or work correctly with the latest chatter release.

## 💡 Why it matters
- Enhances immersion by giving bots distinct, lore-grounded personalities that feel like adventurers.
- Enables dynamic, multi-character conversations that react to the world, combat, quests, and player actions.
- Maintains stable identities and memories, creating continuity across sessions.
- Allows players to customize companion personalities directly in-game without server restarts.

#AI #MMO #Roleplay #Chatbot

---

*Source: [Hokken/mod-llm-chatter](https://github.com/Hokken/mod-llm-chatter)*
