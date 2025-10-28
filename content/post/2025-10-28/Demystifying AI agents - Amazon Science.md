---
title: "Demystifying AI Agents: Understanding the Core Components of Agentic Systems"
description: "A comprehensive guide to understanding AI agents and their core components,
featuring Amazon's AgentCore framework for building autonomous agentic systems that can act on
users' behalf."
date: 2025-10-28T01:20:51.092064+05:30
tags: ["AI Agents", "Amazon Bedrock", "AgentCore", "AWS", "Machine Learning", "LLM", "Agentic AI", "Firecracker", "MicroVMs", "ReAct Model"]
categories: ["Artificial Intelligence", "Cloud Computing", "AWS Services"]
image: "NA"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🤖 Demystifying AI Agents: Understanding the Core Components of Agentic Systems

*Amazon vice president and distinguished engineer Marc Brooker explains how agentic systems work
 under the hood — and how AWS's new AgentCore framework implements their essential components.*

![Amazon Science Video](https://assets.amazon.science/video-placeholder)
*Amazon vice president and distinguished engineer Marc Brooker on Amazon Bedrock AgentCore.*

---

## 🚀 The Rise of Agentic AI

**[Agents](https://www.amazon.science/blog/agents)** are the trendiest topic in AI today, and
with good reason. AI agents act on their users' behalf, autonomously doing things like making
online purchases, building software, researching business trends, or booking travel. By taking
generative AI out of the sandbox of the chat interface and allowing it to act directly on the
world, agentic AI represents a leap forward in the power and utility of AI.

Agentic AI has been moving really fast: for example, one of the core building blocks of today's
agents, the **model context protocol (MCP)**, is only a year old! As in any fast-moving field,
there are many competing definitions, hot takes, and misleading opinions.

To cut through the noise, I'd like to describe the core components of an agentic AI system and
how they fit together. Hopefully, when you've finished reading this post, agents won't seem as
mysterious. You'll also understand why we made the choices we did in designing Amazon Web
Services' **Bedrock AgentCore**, a set of services and tools that lets customers quickly and
easily design and build their own agentic AI systems.

---

## ⚙️ The Agentic Ecosystem

Definitions of the word "agent" abound, but I like a slight variation on the British programmer
Simon Willison's minimalist take:

> *An agent runs models and tools in a loop to achieve a goal.*

The user prompts an AI model (typically a large language model, or LLM) with the goal to be
attained — say, booking a table at a restaurant near the theater where a movie is playing. Along
 with the goal, the model receives a list of the tools available to it, such as a database of
restaurant locations or a record of the user's food preferences. The model then plans how to
achieve the goal and takes a first step by calling one of the tools. The tool provides a
response, and based on that, the model calls a new tool. Through repetitions of this process,
the agent ratchets toward accomplishment of the goal.

### 🧩 Core Components of an Agentic System

An agentic system needs a few core components:

1. **A way to build the agent** - When you deploy an agent, you don't want to have to code it
from scratch. There are several agent development frameworks out there, but I'm partial to
Amazon Web Services' own [Strands Agents](https://github.com/awslabs/strands).

2. **Somewhere to run the AI model** - A seasoned AI developer can download an open-weight LLM,
but it takes expertise to do that right. It also takes expensive hardware that's going to be
poorly utilized for the average user.

3. **Somewhere to run the agentic code** - With frameworks like Strands, the user creates code
for an agent object with a defined set of functions. Most of those functions involve sending
prompts to an AI model, but the code needs to run somewhere.

4. **A mechanism for translating between the text-based LLM and tool calls**

5. **A short-term memory** for tracking the content of agentic interactions

6. **A long-term memory** for tracking the user's preferences and affinities across sessions

7. **A way to trace** the system's execution, to evaluate the agent's performance

--- 
## 🔧 Building an Agent: The ReAct Model

It's well known that asking an LLM to explain how it plans to approach a task improves its
performance on that task. Such "chain-of-thought reasoning" is now ubiquitous in AI.

The analogue in agentic systems is the **ReAct (reasoning + action) model**, in which the agent has:
- A **thought** ("I'll use the map function to locate nearby restaurants")
- Performs an **action** (issuing an API call to the map function)
- Makes an **observation** ("There are two pizza places and one Indian restaurant within two
blocks of the movie theater")

![Agent Development Process](https://assets.amazon.science/dims4/default/5f29cf3/2147483647/strip/true/crop/1080x1080+0+0/resize/1200x1200!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspo
t.s3.amazonaws.com%2Fscience%2F85%2F0b%2F3cd7bc80466c8ed52f56cd2cc5a8%2Fagent-development.gif)
*AgentCore lets the developer use any agent development framework and any model.*

### 💡 Tool Integration and Code Generation

The *tools* available to the agent can include local tools and remote tools such as databases,
microservices, and software as a service. A tool's specification includes a natural-language
explanation of how and when it's used and the syntax of its API calls.

The developer can also tell the agent to build its own tools on the fly. For example, if a tool
retrieves a table stored as comma-separated text and the agent needs to sort it, rather than
waste resources sending it through an LLM repeatedly, the developer can instruct the agent to
generate Python code for such repetitive tasks.

--- 
## ☁️ Runtime Architecture: Firecracker MicroVMs

Historically, there were two main ways to isolate code running on shared servers:
- **Containerization**: Efficient but offered lower security
- **Virtual machines (VMs)**: Secure but came with computational overhead

In 2018, Amazon Web Services' Lambda serverless-computing service deployed
**[Firecracker](https://firecracker-microvm.github.io/)**, a new paradigm offering the best of
both worlds. Firecracker creates "microVMs" with:
- Complete hardware isolation
- Their own Linux kernels
- Reduced overhead (as low as a few megabytes)
- Fast startup times (as low as a few milliseconds)

![AWS AgentCore Architecture](https://assets.amazon.science/dims4/default/d90c4d6/2147483647/strip/true/crop/1080x1080+0+0/resize/1200x1200!/quality/90/?url=http%3A%2F%2Famazon-topics-brightsp
ot.s3.amazonaws.com%2Fscience%2Fb4%2Fa5%2Ff5f50ee842a48ef1e9ea9c58e962%2Fadobe-express-agentcore
-asw-scalable-10-16-toedit-11-45.gif)

AgentCore uses **session-based isolation**, where every session with an agent is assigned its
own Firecracker microVM. When the session finishes, the LLM's state information is copied to
long-term memory, and the microVM is destroyed.

--- 
## 🔗 Tool Calls and Communication Protocols

![AgentCore Gateway](https://assets.amazon.science/dims4/default/1df0f0b/2147483647/strip/true/crop/1038x584+0+0/resize/1200x675!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazo
naws.com%2Fscience%2Fe7%2F5e%2F7b3efa2447c2a1e24c2c15e0ed1e%2Fgateway.png)
*AgentCore Gateway manages the tool calls issued by the agent.*

Just as there are several existing development frameworks for agent creation, there are several
existing standards for communication between agents and tools, the most popular of which is
**MCP (Model Context Protocol)**. MCP establishes:
- Standard format for passing data between the LLM and its server
- A way for servers to describe available tools and data to the agent

In AgentCore, tool calls are handled by the **AgentCore Gateway** service, which:
- Uses MCP by default
- Is configurable and supports a growing set of protocols
- Manages translation between LLM output and tool input specifications

### 🖥️ Computer Use Capabilitie

Sometimes, the necessary tool lacks a public API. In such cases, the only way to retrieve data
is by pointing and clicking on a website. **Computer use** services like Amazon's **Nova Act**
can be used with AgentCore's secure Browser tool, making any website a potential tool for agents.

--- 
## 🧠 Memory Systems

### Short-term Memory

LLMs are next-word prediction engines, with predictions based on long sequences of words they've
 seen, known as *context*. However, agents need additional memory systems beyond just context.

For example, if an agent retrieves information about dozens of restaurants, it doesn't want to
dump all that data into the LLM's context. Instead, it stores the complete list in **short-term
memory** and retrieves specific records based on user preferences and proximity.

### Long-term Memory

Agents must remember prior interactions with clients. If a user previously specified food
preferences, price tolerance, or ambiance preferences, the agent shouldn't need to ask again.

**Long-term memory** features include:
- Storage of user preferences across sessions
- LLM summarization and "chunking" of documents
- Topic-based grouping for easier retrieval
- Configurable strategies for summarization and information extraction

--- 
## 📊 Observability and Monitoring

![AgentCore Observability](https://assets.amazon.science/dims4/default/5ef3a72/2147483647/strip/true/crop/1023x615+0+0/resize/1200x721!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3
.amazonaws.com%2Fscience%2Fb7%2F8a%2F887ef82f4e0cbfa8a702eb7bac73%2Ftraces.png)
*AgentCore Observability lets the customer track an agent's execution.*

Agents are a new kind of software system requiring new approaches to observation, monitoring,
and auditing. Key questions include:
- Are agents running fast enough?
- How much are they costing?
- How many tool calls are they making?
- Are users satisfied with the results?

In **AgentCore Observability**, *traces* provide an end-to-end view of session execution,
breaking down step-by-step which actions were taken and why. These traces are essential for:
- Understanding agent performance
- Providing data to improve agent effectiveness
- Debugging and optimization

--- 
## 🙌 Credits

*Originally posted at: https://www.amazon.science/blog/demystifying-agents*

--- 
## 🏁 Conclusion

This explanation has demystified agentic AI by breaking down its core components: agent building
 frameworks, runtime infrastructure, tool communication protocols, memory systems, and
observability tools. AWS's **AgentCore** provides a comprehensive platform implementing all
these essential components, from **Strands Agents** for development to **Firecracker microVMs**
for secure runtime isolation.

The future of AI lies in agents that can act autonomously on behalf of users, and understanding
these fundamental building blocks is crucial for anyone looking to build or deploy agentic
systems. Whether you're booking restaurants, building software, or researching business trends,
agents represent the next evolution of AI from passive chat interfaces to active, goal-oriented systems.

Ready to build your own agents? All the tools you need are available at the [AgentCore
website](https://aws.amazon.com/bedrock/agentcore/).

--- 
*#AWS #AI #AGENTS #BEDROCK #AGENTCORE #FIRECRACKER #CLOUDCOMPUTING #MACHINELEARNING #LLM
#AGENTIC*

