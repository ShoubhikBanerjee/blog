---
title: "Why AI for Good Depends on Good Data"
description: "Exploring how accessible Earth observation data, AI, and cloud infrastructure can
create a planetary problem-solving machine to address humanitarian challenges and make invisible
 communities visible."
date: 2025-10-28T01:59:33.631962+05:30
tags: ["AI", "Machine Learning", "Open Data", "Humanitarian Technology", "Geospatial Mapping", "Cloud Computing", "Satellite Data", "Social Impact", "OpenStreetMap", "Earth Observation"]
categories: ["AI for Good", "Cloud Computing", "Social Impact"]
image: "https://assets.amazon.science/dims4/default/440e243/2147483647/strip/true/crop/1348x1500+652+0/resize/1200x1335!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2Fe0%2Fee%2F6d1d42764bbfafc894b5ae1b5684%2Fmedium-18-05-w-vogels1771-general.jpg"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🤖 Why AI for Good Depends on Good Data

![Dr. Werner Vogels](https://assets.amazon.science/dims4/default/440e243/2147483647/strip/true/crop/1348x1500
+652+0/resize/1200x1335!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%
2Fscience%2Fe0%2Fee%2F6d1d42764bbfafc894b5ae1b5684%2Fmedium-18-05-w-vogels1771-general.jpg)
*Dr. Werner Vogels is the chief technology officer and vice president of Amazon.*

## 📝 Overview

*This is a condensed version of a talk that Amazon vice president and chief technology officer
Dr. Werner Vogels gave at the AI for Good Global Summit in July 2025 in Geneva.*

New technologies are helping vulnerable communities produce maps that integrate topographical,
infrastructural, seasonal, and real-time data — an essential tool for many humanitarian endeavors.

---

## 🔍 The Data Divide

In January 2007, computer scientist Jim Gray, a Turing Award laureate often described as the
father of modern database systems, disappeared while sailing solo to the Farallon Islands off
San Francisco. Despite deploying every technological resource imaginable, from repositioning
government satellites to mobilizing thousands of recruits through Amazon's Mechanical Turk to
analyze satellite images, we never found him. If we had today's AI resources, would the result
have been different? Maybe. There are things that we can do now that we definitely could not do
in 2007.

While Jim's friends were able to use their private-sector relationships and government
clearances to access real-time satellite data, most vulnerable communities remain invisible in
our digital representations of Earth. The Haiti earthquake of 2010 made this painfully clear.
International rescue teams arrived in Port-au-Prince to find a city that was, for all practical
purposes, unmapped. Emergency responders had GPS coordinates but couldn't navigate because the
maps they had couldn't distinguish between alleys and major roadways or locate critical
infrastructure like hospitals and shelters.

## 🌍 The Invisible Communities

The situation in Haiti isn't unique. Consider Makoko, a community in Lagos, Nigeria, that is
home to more than 300,000 people living on stilt houses in the Lagos Lagoon. On most maps, this
entire community appears as a blank blue spot. These people are effectively invisible, unable to
 access basic services because they don't exist in our spatial data models.

The reason for this omission is simple: most maps are created for commercial purposes, not
humanitarian needs. We meticulously map shopping districts in major cities but leave vast swaths
 of the developing world uncharted. This creates what I call the **"data divide"**, a disparity
in data access that mirrors and exacerbates existing social inequalities.

---

## 🗺️ Multi-Layered Mapping System

Effective maps are multilayered systems operating across different timescales:

| Layer | Description | Update Frequency |
|-------|-------------|------------------|
| **Earth Layer** | Slow-changing geographical features (mountains, rivers) | Decades/centuries
|
| **Infrastructure Layer** | Roads, bridges, buildings | Years |
| **Seasonal Layer** | Vegetation, water levels, environmental factors | Seasonal |
| **Real-time Layer** | Human activity, weather patterns, emergencies | Constant |

![Unmapped Communities](https://assets.amazon.science/dims4/default/78d29c9/2147483647/strip/true/crop/1920
x1080+0+0/resize/1200x675!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.co
m%2Fscience%2Fed%2F74%2F9bc440354f21bc5551ab2fcc647d%2Funmapped-amzsci-hero-dark-a.jpg)

--- 
## 📡 Democratizing Earth Data

The good news is that the tools for data collection have become much more accessible. The number
 of Earth observation satellites has exploded from about 150 in 2008 to over **10,000** today.
These satellites offer not just high-resolution imagery but advanced sensors like multispectral
imagers, radar, and lidar.

### 🚁 Community-Driven Mapping

In the aftermath of the Haiti earthquake, roughly 600 members of the OpenStreetMap community
were able to create the first reliable crisis map within **48 hours**. It only took two days to
go from unmapped to mapped. This crowdsourced map became the default navigation tool for every
major responding organization, from the UN to the US Marine Corps.

The Mapping Makoko project trained local residents to pilot drones and map their community. This
 initiative did more than create a map; it empowered residents with a tool for political
advocacy, demonstrating the power of democratized data collection.

![Aerial footage of Mokoko](https://assets.amazon.science/dims4/default/2e8e07c/2147483647/strip/true/crop/1430x748+0+0/resize/1200x628!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s
3.amazonaws.com%2Fscience%2Ffa%2F88%2F40d4abb9491aa52fdb00c437adee%2Fpicture3.jpg)
*Aerial footage of Mokoko captured by a drone piloted by a local resident.*

--- 
## 🏥 Building with Open Data

During a recent visit to Rwanda, I saw firsthand how data-driven mapping can transform
healthcare delivery. The Rwanda Health Intelligence Center uses real-time data to track
healthcare utilization across the country. By combining this with geospatial data, they've
calculated the maximum walking distance for pregnant women to reach a health center.

![Rwanda Health Intelligence
Center](https://assets.amazon.science/dims4/default/1c6c53b/2147483647/strip/true/crop/2048x1365+0+0/resize/1200x800!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fs
cience%2F32%2F8b%2F23831d1344539f5549fc0422fb51%2F54428974370-437d97403c-k.jpg)
*Image of the Rwanda Health Intelligence Center.*

Another inspiring example is the [Ocean Cleanup](https://theoceancleanup.com/) project, which
aims to remove 90% of ocean plastic by 2040. They've developed a river model using drones, AI
analysis, and GPS-tagged dummy plastics to predict plastic-flow patterns.

--- 
## 🌐 Planetary Problem-Solving Machine

The combination of open data, advanced AI models, and cloud infrastructure creates what I call a
 **planetary problem-solving machine**. This trio can tackle challenges that were previously intractable:

- **Open data** ensures transparency and verifiability
- **AI** extracts insights that would be impossible for humans to discern
- **Cloud infrastructure** provides the scale needed to process petabytes of data

When we have data that could save lives or protect the environment, keeping it private is
morally indefensible. The [United Nations' 17 Sustainable Development
Goals](https://sdgs.un.org/goals) all depend on geospatial data.

### 💡 The Now Go Build CTO Fellowship

In 2024, I launched the [Now Go Build CTO Fellowship](https://www.amazon.com/now-go-build),bringing together technology leaders from non-profits and social good organizations working to
address:

- 🌱 Climate change
- 🚨 Disaster management
- 🏥 Healthcare accessibility
- 🍽️ Food securit
- 📚 Education

These Fellows are using data to solve the world's hardest problems, whether measuring crop
yields, connecting surplus food with charities and families, or piloting drones in conflict
areas — none of which is possible without maps.

--- 
## 🙌 Credits

*Originally posted at: https://www.amazon.science/blog/why-ai-for-good-depends-on-good-data*

--- 
## ✅ Final Thoughts

Maps have always been more than navigation tools: they're instruments of power. In the digital
age, they're becoming tools of justice, healthcare, and environmental protection. By making the
invisible visible, we can create a more equitable world.

The question for all of us is: **What data do we have that could be useful to others?** And more
 importantly, **what data can we open up?**

If we don't act, we risk perpetuating a world where the most vulnerable remain invisible, where
disasters are compounded by lack of information, and where progress is measured only in places that are profitable.

Now go build. 🚀

--- 
*#AI #MACHINELEARNING #OPENDATA #HUMANITARIAN #MAPPING #SUSTAINABILITY #GEOSPATIAL
#CLOUDCOMPUTING #SOCIALIMPACT*

