---
title: "Datasette Adds Chart Annotations for Enhanced Data Visualization"
slug: "datasette-adds-chart-annotations-for-enhanced-data-visualization"
description: "I added chart annotations to datasette-charts! You can now render a chart and then annotate it with lines, shaded areas, labels, or a combination of the three."
date: 2026-11-26T18:08:23+05:30
tags: [Datasette, datavisualization, annotations, charts]
categories: ["AI", "Data Visualization", "Software Development"]
image: "https://static.simonwillison.net/static/2026/chart-annotate.gif"
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Adds Chart Annotations for Enhanced Data Visualization

I added chart annotations to datasette-charts! You can now render a chart and then annotate it with lines, shaded areas, labels, or a combination of the three.

## 📊 What’s New
- Add lines, shaded areas, labels, or any combination
- Works in both standard Datasette and Datasette Lite
- Interactive annotation editing in the chart builder UI

## 🧪 How It Works
A chart with annotations looks like this:

![Chart with annotations](https://static.simonwillison.net/static/2026/chart-with-annotations.webp)

Same chart in Datasette Lite lets you tweak annotations using the chart builder UI.

## 🤖 Agent Integration
If you also install Datasette Agent the agent can build annotated charts for you. Here's what I got on the agent.datasette.io demo for this prompt: 'Show a chart comparing Simon's tagged content about LLMs with his tagged content about Datasette, with annotations'

## 🚀 Availability
The feature is now available in datasette-charts. Datasette Agent support requires the additional plugin installation for automated chart generation.

![figure](https://static.simonwillison.net/static/2026/chart-with-annotations.webp)

#Datasette #data-visualization #annotations #charts

---

*Source: [Release: datasette-charts 0.3a0](https://simonwillison.net/2026/Nov/25/datasette-charts/)*
