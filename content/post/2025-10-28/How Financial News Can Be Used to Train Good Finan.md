---
title: "How Financial News Can Be Used to Train Good Financial Models"
description: "Exploring how financial news narratives can be structured and used to train
predictive models for stock market movements using classification, RAG, and reinforcement
learning approaches."
date: 2025-10-28T02:01:05.699880+05:30
tags: ["finance", "machine-learning", "nlp", "stock-prediction", "rag", "reinforcement-learning", "fintech", "ai", "sentiment-analysis", "grpo"]
categories: ["Finance", "Machine Learning", "AI"]
image: "https://cdn-uploads.huggingface.co/production/uploads/683ef46c2695302d716db7b9/9lvyh3l9PU2samPrQHScp.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 📈 How Financial News Can Be Used to Train Good Financial Models

I've always loved finance and economics; that's why they have been the focus of all my studies.
It's also why I've always kept myself updated on what's happening in the world, mainly from a
market perspective. I have always read the Financial Times, Bloomberg, The Economist, CNBC, and publications like that.

The interesting part is that they feature some excellent columnists and frequently interview
experts. They really know what's going on in the world, and from an academic perspective, their
analyses are usually quite accurate. Of course, you need to follow the right columnists,
sections, and newspapers. But many of them are quite good.

With this introduction, I just wanted to emphasize the **quality** of the *narrative*.

**Financial news usually narrates past events**. For example, when DeepSeek published a new AI
without using NVIDIA's chips, columnists didn't just report the drop in NVIDIA's stock price;
they also explained the reasons behind it, and why some companies, such as Apple, were not affected.

From the news, we can thus extract the *reasons* behind certain stock movements, which are often
 very well explained. By identifying statements like "NVIDIA stock dropped" and labeling them as
 "Down," we can begin to capture structured information from financial narratives.

---

## 🎯 Classification Models: Capturing Market Signals

The first step in building predictive models was to structure the raw news data. Each article
was associated with:

- Date
- Company name
- Title and summary of the news

A classification model was trained using the structured dataset and the direction of the price
variation extracted from the news. The trained model processed news summaries and predicted the
corresponding price movement label. The results showed that aggregated over time, model outputs
closely tracked actual monthly price changes for companies like Apple, Tesla, Microsoft, and
Meta, as well as for broader indices like the Nasdaq.

You can check it here: https://huggingface.co/spaces/SelmaNajih001/SentimentAnalysis

### 📊 Nasdaq and Sentiment

![Nasdaq sentiment analysis chart](https://cdn-uploads.huggingface.co/production/uploads/683ef46
c2695302d716db7b9/9lvyh3l9PU2samPrQHScp.png)

*Chart showing correlation between Nasdaq performance and sentiment analysis predictions*

### 🍎 Apple Stock and Sentiment

![Apple stock sentiment analysis](https://cdn-uploads.huggingface.co/production/uploads/683ef46c
2695302d716db7b9/T00KQ8KjGmKJd5yEDu3Qr.png)

*Apple stock price movements tracked against sentiment predictions*

### 🚗 Tesla Stock and Sentiment

![Tesla stock sentiment analysis](https://cdn-uploads.huggingface.co/production/uploads/683ef46c
2695302d716db7b9/CUL19D62YbNc23YAnhFsz.png)

*Tesla's volatile stock performance correlated with news sentiment*

You can try it in the Space, but the similarity of the trends is particularly strong for
volatile companies, such as Tesla, or in years with higher overall volatility. This is just a
hypothesis, but I believe that the more volatile the price, the more the news will focus on it;
otherwise, they would discuss topics related to the company without mentioning its price
movements.

> In conclusion, the key insight is that financial news is not just descriptive: it is
explanatory. By converting qualitative narratives into structured labels, the model can identify
 causal relationships between events and market responses.

---

## 🚀 Beyond Classification: Event Prediction and Context-Aware Models

While classification captures the reaction to news, a more ambitious goal is to predict which
companies are affected by a given event, by *how much*, and *why*. This requires reasoning about
 events, not just labeling observed outcomes.

Retrieval-augmented generation (RAG) enables this. The approach allows the model to reference
historical events when predicting outcomes for new events. For instance: If a new AI competitor
emerges, the model can reference past AI developments and their market impacts. Using historical
 context, it predicts which companies are likely to be affected, the expected price changes, and
 generates explanations consistent with previous patterns.

> This mirrors how investors operate: they analyze past outcomes, monitor news, and use
correlations to anticipate future movements.

## ⚙️ GRPO and Reinforcement Learning for Enhanced Accuracy

To further refine predictions, a reinforcement learning framework called Group Relative Policy
Optimization (GRPO) was applied. The model received rewards based on its prediction accuracy:

- **4 points** for correctly predicting both the affected stock and price change
- **2 points** for partially correct predictions
- **0 points** for incorrect predictions

This incentivized the model to learn not only correlations but also the magnitude of expected
market reactions, improving performance over simple classification or context-free prediction.

The dataset included:

- Summaries of central bank speeches (ECB and US Federal Reserve)
- News summaries with labeled causes and price variations
- Company identifiers for context

You can find it here:
https://huggingface.co/datasets/SelmaNajih001/FinancialNewsAndCentralBanksSpeeches-Summary-Rag

Using this rich dataset, the model learned patterns like:

- How regulatory announcements influence sector-specific stocks
- How competitive developments impact companies differently depending on prior investment
exposure

The results showed substantial improvements in prediction accuracy, especially when the model
had access to historical context via RAG.

Try it: https://huggingface.co/spaces/SelmaNajih001/StockPredictionExplanation

A few examples of the output:

![Stock prediction example 1](https://cdn-uploads.huggingface.co/production/uploads/683ef46c2695302d716db7b9/9QTbcvzeZW3IOeo36O7GG.png)

![Stock prediction example 2](https://cdn-uploads.huggingface.co/production/uploads/683ef46c2695302d716db7b9/vd_SB6GHL23uIfhkhP1NN.png)

*Examples showing the model's prediction outputs with explanatory reasoning*

It actually usually goes on in the generation of the text. I find it interesting how it searches
 for similar events, but this happens because of a mistake I made during training. To be honest,
 I've spent too much money on it to redo the training.

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/SelmaNajih001/llms-applied-to-finance*

## 🏁 Conclusion

Financial news contains not just descriptive content but rich, explanatory narratives that
reveal why the market moves. By structuring this information and leveraging LLMs, it is possible to:

- Extract meaningful facts from tens of thousands of articles
- Map events to price movements for specific companies
- Predict future impacts with contextual reasoning
- Provide explanations that mirror human analysis

Combining classification models, RAG-enhanced event prediction, and reinforcement learning
(GRPO) creates a comprehensive framework for analyzing the market. LLMs allow us to move beyond
historical price data into a space where textual information drives actionable financial
insight, bridging the gap between qualitative analysis and quantitative modeling.

> In essence, these methods show that the "why" behind market movements is as important and
accessible as the "what," enabling investors and analysts to anticipate and understand market
behavior with unprecedented granularity.

*#FINANCE #MACHINELEARNING #NLP #STOCKPREDICTION #RAG #REINFORCEMENTLEARNING #FINTECH #AI*

