---
title: "RTranslator: Offline Real-Time Translation App for Android"
slug: "rtranslator-offline-real-time-translation-app-for-android"
description: "RTranslator is an (almost) open-source, free, and offline real-time translation app for Android. It allows users to have conversations in real-time, even if they speak different languages."
date: 2026-11-19T22:12:49+05:30
tags: [RTranslator, RealTimeTranslation, AndroidApp, OpenSource, OfflineTranslation]
categories: ["AI", "Mobile Applications", "Artificial Intelligence", "Translation Technology"]
image: "https://avatars.githubusercontent.com/u/32955129?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# RTranslator: Offline Real-Time Translation App for Android

RTranslator is an (almost) open-source, free, and offline real-time translation app for Android. It allows users to have conversations in real-time, even if they speak different languages.

## 🔍 Overview
- RTranslator is a free, offline real-time translation app for Android.
- It uses Meta's NLLB for translation and OpenAi's Whisper for speech recognition.
- The app works even in the background, with the phone on standby or when using other apps.

## 🧩 How it works
- The app has two main features: Conversation mode and WalkieTalkie mode.
- In Conversation mode, you can connect with another phone that uses the app.
- When you talk, your phone (or the Bluetooth headset, if connected) will capture the audio.
- The audio captured will be converted into text and sent to the interlocutor's phone.
- The interlocutor's phone will translate the text received into his language.
- The interlocutor's phone will convert the translated text into audio and will reproduce it from its speaker (or by the Bluetooth headset of the interlocutor if connected).
- In WalkieTalkie mode, the smartphone microphone will listen in two languages simultaneously.
- The app will detect in which language the interlocutor is speaking, translate the audio into the other language, convert the text into audio, and then reproduce it from the phone speaker.

## ⚙️ Key details
- Each user can have more than one connected phone so that you can translate conversations between more than two people and in any combination.
- The app only translates conversations between two people, it doesn't work with Bluetooth headsets, and you have to talk in turns.
- It's not a real simultaneous translation, but it can work with only one phone.
- RTranslator uses Meta's NLLB for translation and OpenAi's Whisper for speech recognition, both are (almost) open-source and state of the art AIs, have excellent quality and run directly on the phone, ensuring absolute privacy and the possibility of using RTranslator even offline without loss of quality.
- The 3.0 version of RTranslator is currently funded through the [NGI Mobifree Fund], a fund established by [NLnet].
- The NLLB translation model has been replaced with the option to choose between: Mozilla Bergamot models, Madlad 400 3B, and HY-MT 1.5 1.8B.
- All these models have better translation quality than NLLB 54B, similar to Google Translate, with HY-MT 1.5 1.8B having much better scores than Google Translate, similar to DeepSeek v3 and Gemini 3.0.
- MLKit has been replaced with open-source alternatives (FastText and Lingua), making RTranslator 100% open-source.

## 🚀 Availability
- To install the app, download the latest version of the app apk file from https://github.com/niedev/RTranslator/releases/ and install it.
- On the first launch, RTranslator will automatically download the models for translation and speech recognition (1.2GB) and once done you can start translating.
- The initial download will get the models from GitHub, however in some regions GitHub is very slow, those who have problems of this kind can download the models separately from a computer (or in general in whatever way they prefer) and insert them manually into the app following this guide.

## 💡 Why it matters
- RTranslator offers a unique solution for real-time translation, ensuring absolute privacy and the possibility of using the app even offline.
- The app's use of state-of-the-art AI models for translation and speech recognition ensures excellent quality.
- RTranslator is funded through the [NGI Mobifree Fund], a fund established by [NLnet], which shows the potential and impact of the app.
- The app's 100% open-source nature, with the replacement of MLKit with open-source alternatives, makes it a significant step forward in the field of real-time translation apps.


#RTranslator #RealTimeTranslation #AndroidApp #OpenSource #OfflineTranslation

---

*Source: [niedev/RTranslator](https://github.com/niedev/RTranslator)*
