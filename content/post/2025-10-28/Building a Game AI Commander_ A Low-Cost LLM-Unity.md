---
title: "Building a Game AI Commander: A Low-Cost LLM-Unity Communication Pipeline for Independent Game Developers"
description: "Exploring a hierarchical AI architecture that uses LLMs as strategic commanders
rather than direct NPC controllers, achieving sophisticated game AI behavior at just $0.58 for
454 API calls."
date: 2025-10-28T00:43:58.542381+05:30
tags: ["Unity", "LLM", "Game Development", "AI", "Machine Learning", "Game AI", "Architecture", "Indie Games", "DeepSeek", "Command Pattern"]
categories: ["Game Development", "Artificial Intelligence", "Software Architecture"]
image: "https://cdn-uploads.huggingface.co/production/uploads/68fb0399fee74d154b69abb5/i3Qdlusu19tHtJe2mJBqt.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🎮 Building a Game AI Commander: A Low-Cost LLM-Unity Communication Pipeline for Independent
Game Developers

![9-grid testbed in unity](https://cdn-uploads.huggingface.co/production/uploads/68fb0399fee74d154b69abb5/i3Qdlusu19tHtJe2mJBqt.png)
*Testing environment showcasing the AI Commander system in Unity*

If you're an indie game developer, you've probably felt the tension: you want to create enemies
with smart, unpredictable, strategic behavior, but the complexity and cost of advanced AI feel
out of reach. Traditional behavior trees can become predictable, and integrating a Large
Language Model (LLM) for every NPC's decision seems like a quick way to empty your bank account.

For my Master's research at RMIT University, I explored a different approach: What if an LLM
wasn't a pawn, but a commander?

This post walks through the "AI Commander," a practice-based research project where I built a
low-cost communication pipeline between Unity and an external LLM. I'll cover the architecture,
the prompt engineering, and the surprising results—including how 454 API test calls cost me just $0.58 USD.

## ⚠️ The Problem: Intelligence vs. Cost

Traditional game AI, like State Machines and Behavior Trees, is reliable but deterministic.
Players are incredibly good at learning and exploiting patterns, which can reduce a game's long-term replayability.

LLMs offer a solution with their incredible reasoning capabilities. However, for a small
developer, direct real-time control of NPCs via API calls introduces three critical problems:

**High Latency**: Round-trip API calls can take hundreds of milliseconds, which is unacceptable
for a real-time game.

**Prohibitive Cost**: LLMs are priced per token. Constant API calls from multiple NPCs would be
economically unsustainable.

**Lack of Controllability**: LLMs can "hallucinate," producing inconsistent or nonsensical
output, making stable NPC behavior difficult to guarantee.

## 🧩 Our Solution: A Two-Layer "AI Commander" Architecture

To solve this, I designed a hierarchical system that separates high-level strategy from low-level execution.

**The Strategic Reasoning Layer (The LLM)**: An external LLM (I used DeepSeek) acts as the
"brain." It operates asynchronously, receiving a simplified, high-level snapshot of the
battlefield every few seconds. Its only job is to analyze the situation and issue a strategic
command, like "Unit 3, move to Zone 5."

**The Tactical Execution Layer (Unity)**: The game's NPCs run on simple, traditional,
locally-run state machines—the "muscles." Their only job is to receive a concrete command from
the commander and execute it immediately and reliably.

This separation is the key to solving the cost and latency issues. The LLM is only called
periodically for major tactical decisions, not for every frame or every small action.

To bridge these two layers, I used the Command Pattern. The LLM's output is a simple, structured
 JSON object that represents a command. A Command Processor in Unity parses this JSON and
dispatches the order to the correct NPC.

![complete communication pipeline architecture](https://cdn-uploads.huggingface.co/production/uploads/68fb0399fee74d154b69abb5/7oaNS-MG866dGA1nCgtSY.png)
*Complete communication pipeline architecture diagram*

## ⚙️ Making it Work: "Natural Language Programming" in Unity

The core of the pipeline is its Prompt Engineering system. I used Unity's ScriptableObject to
create highly configurable prompt templates. A dedicated PromptBuilder class then injects
real-time game data (like squad status and enemy locations) into these templates before sending them to the API.

This modular approach treats prompt construction as a form of "natural language programming."
Here's a look at the core logic of the PromptBuilder:

```csharp
public static class PromptBuilder {
    public static string BuildSquadState(PromptProfileSO profile, Dictionary<string, string> data) {
        // 1. Start with the main template from the ScriptableObject
        StringBuilder promptBuilder = new StringBuilder(profile.promptTemplate);

        // 2. Populate the rules section first StringBuilder rulesBuilder = new StringBuilder(profile.rulesSection);
        // ... (Inject dynamic rules like min/max IDs) promptBuilder.Replace("{rules}", rulesBuilder.ToString());

        // 3. Replace all data placeholders (e.g., {squad_state}, {enemy_data}) foreach (var kvp in data) {
            promptBuilder.Replace($"{{{kvp.Key}}}", kvp.Value);
        }

        // 4. Append the schema for clear instructions promptBuilder.Append("\n\n--- REQUIRED OUTPUT FORMAT ---\n");
        promptBuilder.Append("You must strictly return a JSON object that adheres to the following schema:");
        promptBuilder.Append(profile.schemaJson);

        return promptBuilder.ToString();
    } }
```

## 📊 Key Observations from 4 Months of Testing

After building the prototype in a simplified 9-grid testbed, I ran tests over four months. Here
are the most important findings:

### 1. The Pipeline is Functional and Remarkably Cheap 💰

The system consistently executed the core loop: abstracting game state, sending it to the LLM,
and parsing the JSON command in return. The total operational cost for 454 API calls and over
430k tokens was just ¥0.67 CNY (about $0.58 USD).

![Cost Analysis](https://cdn-uploads.huggingface.co/production/uploads/68fb0399fee74d154b69abb5/sxRYc1GE7qaWiWUblSDEI.png)
*Cost breakdown showing exceptional affordability*

### 2. The AI Demonstrated Emergent, Unscripted Behavior 🤖

This was the most intriguing finding. The LLM repeatedly issued "Hold" commands—telling a unit
to stay in its current position. This was likely a conservative strategy when it was uncertain
about the player's location. Critically, the "hold" command was never pre-programmed or
explicitly defined in the prompts. The AI reasoned that sometimes the best move is no move at all.

### 3. It Showcased Glimpses of Genuine Tactical Reasoning 🎯

When a unit was lost while the player's location was unknown, the LLM generated commands to
consolidate forces around a key defensive area. When the player's location was inferred, it
issued a series of "Move" commands to encircle that area. These were logical, non-scripted conservative tactics.

![Hold Command](https://cdn-uploads.huggingface.co/production/uploads/68fb0399fee74d154b69abb5/BiOpdokg-rDgy-QghgFdt.png)
*"Hold" Command demonstration*

![Surround Command](https://cdn-uploads.huggingface.co/production/uploads/68fb0399fee74d154b69abb5/CRLxBG412hGkxpzjj-NOc.png)
*"Surround" Command tactical execution*

## ⚠️ Limitations

It's important to be clear: this was an exploratory study, not a production-ready system. The
test environment was highly simplified, and there was no direct comparative analysis against a
traditionally scripted AI. The goal was to investigate the practical feasibility and observe initial phenomena.

## 💻 Resources and Links

For a deeper dive into the methodology, data, and full discussion, check out these resources:

**💻 Explore the Core Code and Read the Full Paper on GitHub:**
[https://github.com/AlexMercerDUODUO/AI-Commander-Unity-LLM-Exploratory-Research-RMIT-MAGI]

**🎮 Play the Demo on Itch.io:**
[https://alexduo.itch.io/humanexe-ai-commander]

**▶️ Watch the Full Video Essay on YouTube:**
[https://www.youtube.com/watch?v=tYeDCry3vtY]

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/AlexDuo/llm-unity-ai-commander*

## 🏁 Conclusion

The "AI Commander" model appears to be a promising and economically viable approach for
developers with limited budgets. It suggests that the future of dynamic game AI may not lie in
raw computational power, but in clever, accessible architectures that facilitate a creative
dialogue between game engines and the emergent power of Large Language Models.

This research demonstrates that indie developers can harness the strategic intelligence of LLMs
without breaking the bank, opening new possibilities for creating more engaging, unpredictable,
and tactically sophisticated game experiences. The key lies in smart architectural decisions
that separate strategic reasoning from tactical execution, creating a cost-effective bridge
between cutting-edge AI and practical game development.

_#GAMEDEV #UNITY #LLM #AI #INDIEGAMES #MACHINELEARNING #GAMEAI #RESEARCH #ARCHITECTURE #LOWCOST_

