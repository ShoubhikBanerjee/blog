---
title: "GPT-6 Astra and ChatGPT Work Generate Custom Running Routes Using OSM Data"
slug: "gpt-6-astra-and-chatgpt-work-generate-custom-running-routes-using-osm-data"
description: "A user demonstrated the ability of ChatGPT Work with GPT-6 Astra (Max) to generate specific 5K and 10K running routes that loop from a provided home address using OpenStreetMap (OSM) data."
date: 2026-09-13T06:06:36+05:30
tags: [GPT6, ChatGPTWork, OpenStreetMap, AIAgents]
categories: ["AI", "Artificial Intelligence", "Software Development", "AI Agents"]
image: "https://static.simonwillison.net/static/2026/5k-route.webp"
author: "Shoubhik Banerjee"
draft: false
---

# GPT-6 Astra and ChatGPT Work Generate Custom Running Routes Using OSM Data

A user demonstrated the ability of ChatGPT Work with GPT-6 Astra (Max) to generate specific 5K and 10K running routes that loop from a provided home address using OpenStreetMap (OSM) data.

## 🧩 How it works
To create the routes, the system performed the following steps:
* Used Nominatim to locate the user's address.
* Used Overpass to download local OpenStreetMap roads and trails.
* Calculated the loops locally.
* Utilized a visualize skill to display the map.

## ⚙️ Key details
* **Output Formats**: The system produced an embedded visualization, downloadable GPX files, and GeoJSON files.
* **Visualization Method**: The system created an HTML file (`/workspace/el-granada-5k-share.html`) embedded in the UI. This file uses D3, loaded from an allow-listed CDN, and a `<script type="application/json">` element containing the geometry for the route and map.
* **Allow-listed CDNs**: The Content Security Policy (CSP) allows the following origins:
    * cdnjs.cloudflare.com
    * esm.sh
    * cdn.jsdelivr.net
    * unpkg.com
    * fonts.googleapis.com
    * fonts.gstatic.com
    * fonts.bunny.net
* **Performance**: The process took 27 minutes to complete.

## 💡 Why it matters
This case highlights a limitation regarding transparency and data persistence in LLM systems. The user reported that the actual code executed by the AI was not visible in the ChatGPT UI. Furthermore, because the thread had been compacted, ChatGPT was unable to provide a copy of the Python code used to generate the routes when requested.

#GPT-6 #ChatGPTWork #OpenStreetMap #AIAgents

---

*Source: [Generating running routes with GPT-6 Astra and ChatGPT Work](https://simonwillison.net/2026/Sep/12/astra-running-routes/)*
