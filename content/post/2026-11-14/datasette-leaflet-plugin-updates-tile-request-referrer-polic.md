---
title: "Datasette-Leaflet plugin updates tile request referrer policy"
slug: "datasette-leaflet-plugin-updates-tile-request-referrer-policy"
description: "On 13th November 2026, an update was released for the datasette-leaflet plugin to ensure compliance with OpenStreetMap’s tile server policy regarding referrer headers."
date: 2026-11-14T18:03:06+05:30
tags: [Datasette, OpenStreetMap, Leaflet, WebDevelopment, HTTP]
categories: ["AI", "Software Development", "Data Tools", "Web Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# Datasette-Leaflet plugin updates tile request referrer policy

On 13th November 2026, an update was released for the datasette-leaflet plugin to ensure compliance with OpenStreetMap’s tile server policy regarding referrer headers.

## ⚙️ Key details

* OpenStreetMap requires that requests to their hosted tile server include a referrer header.
* Previously, Datasette table pages used the `Referrer-Policy: no-referrer` HTTP header, which caused plugins loading tiles from OpenStreetMap to violate this policy.
* Datasette-leaflet is a plugin that bundles Leaflet for use by other Datasette plugins.

## 💡 Why it matters

* The plugin now explicitly sets the referrer policy on tile requests to `strict-origin-when-cross-origin`.
* This update allows the host information to be passed while withholding the full path to the page, satisfying OpenStreetMap requirements.

#Datasette #OpenStreetMap #Leaflet #WebDevelopment #HTTP

---

*Source: [Release: datasette-leaflet 0.3](https://simonwillison.net/2026/Nov/13/datasette-leaflet/)*
