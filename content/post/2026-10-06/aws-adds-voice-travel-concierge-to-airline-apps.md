---
title: "AWS Adds Voice Travel Concierge to Airline Apps"
slug: "aws-adds-voice-travel-concierge-to-airline-apps"
description: "Amazon Web Services has published guidance for adding a voice-operated travel concierge to airline applications, built on three managed services: Amazon Bedrock AgentCore, Amazon Nova Sonic on..."
date: 2026-10-06T22:08:14+05:30
tags: [AWS, VoiceAI, Bedrock, AIAgents, TravelTech]
categories: ["AI", "AI Agents", "Voice Technology", "Cloud Computing", "Travel"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/24/ML-21469-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Adds Voice Travel Concierge to Airline Apps

Amazon Web Services has published guidance for adding a voice-operated travel concierge to airline applications, built on three managed services: Amazon Bedrock AgentCore, Amazon Nova Sonic on Bedrock, and Amazon Bedrock Knowledge Bases. The concierge allows travelers to check flights, change seats, and manage bookings through natural spoken requests without leaving the app or navigating screens.

## 🔍 Overview
Airlines already have apps and websites where travelers check flights, pick seats, and manage bookings. Adding a natural voice layer opens those tasks to spoken requests. With this voice layer, a traveler can change a seat or check a delay by speaking, without leaving the app or navigating through screens. The concierge runs alongside existing screens rather than replacing them, so travelers move between tapping and talking in the same session.

## 🧩 How It Works
The traveler speaks, and the concierge pulls up their itinerary, changes a seat, updates a meal preference, answers a policy question, and connects them to a live agent on request. The user opens the web application, hosted on AWS Amplify, in a browser or on a mobile device. Amazon Cognito authenticates the request and returns JSON Web Tokens (JWTs) and temporary AWS credentials. The front end opens a SigV4-signed WebSocket connection to Amazon Bedrock AgentCore to begin the voice concierge session. The runtime validates the token with Amazon Cognito and initializes Amazon Nova 2.5 Sonic through Amazon Bedrock. Amazon Nova 2.5 Sonic processes the audio and triggers tool calls. The AgentCore Gateway forwards requests as REST API calls to Amazon API Gateway, which routes them to AWS Lambda functions. AWS Lambda functions query Amazon DynamoDB tables for bookings, passengers, seat maps, loyalty status, and flight information.

## ⚙️ Key Details
- **Amazon Bedrock AgentCore** is an agentic platform for building, deploying, and operating AI agents securely at scale with your choice of framework and model. The AgentCore runtime hosts the agent with microVM isolation per session. AgentCore Gateway exposes backend endpoints as discoverable MCP tools.
- **Amazon Nova Sonic on Bedrock** is a speech-to-speech model for real-time voice. This implementation uses Amazon Nova 2.5 Sonic for real-time speech.
- **Amazon Bedrock Knowledge Bases** is a fully managed retrieval augmented generation service that grounds answers in your own documents. It answers policy questions by grounding responses in your airline policy documents.
- The system streams audio in both directions and holds the thread of a conversation across many turns.
- The architecture separates the front end, the AI agent, and the backend services into distinct layers, so you can develop and scale each one on its own.
- MCP (Model Context Protocol) is an open standard for connecting AI applications to external tools and data.
- The AI layer connects to a sample airline backend with synthetic data, which accelerates your implementation when you adapt the pattern to your own systems.
- The backend uses AWS Lambda for business logic (itineraries, seat maps, passenger updates, flight status, loyalty, policy lookups, and escalation) and Amazon DynamoDB for data storage (customer profiles, bookings, passengers, seat maps, purchase history, preferences, conversations, and flight data).

## 🚀 Availability
The solution is deployed by building an agent with the Strands Agents framework and Amazon Nova 2.5 Sonic for real-time speech, hosted on AgentCore runtime, a capability of the Amazon Bedrock AgentCore framework. It connects to backend services with the Model Context Protocol (MCP) through AgentCore Gateway, a capability of Amazon Bedrock AgentCore. Developers deploy a voice AI concierge on AWS using the AWS Cloud Development Kit (AWS CDK). The services scale on demand, so organizations spend time on the experience instead of the infrastructure.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/24/ML-21469-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/24/ML-21469-4.gif)

#AWS #VoiceAI #Bedrock #AIAgents #TravelTech

---

*Source: [Build a voice travel concierge with Amazon Bedrock AgentCore, Managed Knowledge Base and Nova Sonic | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-voice-travel-concierge-with-amazon-bedrock-agentcore-managed-knowledge-base-and-nova-sonic/)*
