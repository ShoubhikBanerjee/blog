---
title: "New Datasette Geospatial Plugin Built with Claude Fable 5.2 and OpenFreeMap"
slug: "new-datasette-geospatial-plugin-built-with-claude-fable-5-2-and-openfreemap"
description: "On 15th November 2026, a new geospatial plugin for Datasette was released, marking the first such addition in a significant period. The tool integrates the MapLibre GL library with OpenFreeMap, a..."
date: 2026-11-16T18:20:32+05:30
tags: [Datasette, Geospatial, ClaudeAI, OpenFreeMap, MapLibreGL]
categories: ["AI", "Software Development", "Artificial Intelligence", "Geospatial Technology"]
image: "https://static.simonwillison.net/static/cors-allow/2026/datasette-maplibre.webp"
author: "Shoubhik Banerjee"
draft: false
---

# New Datasette Geospatial Plugin Built with Claude Fable 5.2 and OpenFreeMap

On 15th November 2026, a new geospatial plugin for Datasette was released, marking the first such addition in a significant period. The tool integrates the MapLibre GL library with OpenFreeMap, a free vector map server operated by Zsolt Ero.

## 🔍 Overview
Most of the plugin was developed using a single prompt provided to Claude Fable 5.2. The AI was instructed to analyze the `datasette-cluster-map` and `datasette-leaflet-geojson` plugins alongside a local demo file to build a new tool that combines their features.

## 🧩 How it works
The development process resulted in several specific features derived from a prompt to "be creative and think outside the box."

* Displays SVG previews of GeoJSON shapes initially.
* Loads a WebGL preview only when shapes scroll into view.
* Displays GeoJSON shapes and latitude/longitude points together on the same map.

## 🚀 Availability
A comprehensive demo page has been released that functions in the latest version of Datasette Lite. This allows users to load the plugin and a demo database directly in a web browser using Pyodide and WebAssembly.

#Datasette #Geospatial #ClaudeAI #OpenFreeMap #MapLibreGL

---

*Source: [Release: datasette-maplibre 0.1a0](https://simonwillison.net/2026/Nov/15/datasette-maplibre/)*
