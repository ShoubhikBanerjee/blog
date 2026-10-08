---
title: "Robots Assemble NVIDIA GB300 Tester Trays with High Precision"
slug: "robots-assemble-nvidia-gb300-tester-trays-with-high-precision"
description: "The NVIDIA Seattle Robotics Lab (SRL) and the NVIDIA Isaac engineering team tackled the problem of building intelligent robots that can assemble GB300 tester trays – a critical step before shipping..."
date: 2026-10-08T22:04:21+05:30
tags: [NVIDIA, Robotics, Automation, AIHardware]
categories: ["AI", "Robotics", "Artificial Intelligence", "Manufacturing Automation", "Computer Vision"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image-1790985193398-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Robots Assemble NVIDIA GB300 Tester Trays with High Precision

The NVIDIA Seattle Robotics Lab (SRL) and the NVIDIA Isaac engineering team tackled the problem of building intelligent robots that can assemble GB300 tester trays – a critical step before shipping the NVIDIA Grace Blackwell GB300 superchip.

## 🤖 Overview
- The GB300 superchip is the engine of AI training and inference for modern foundation models. 
- SRL asked the central question: *Can we build intelligent robots to assemble such complex systems?* 
- Assembling GB300 trays is described as one of the hardest problems SRL has tackled in nine years.

## 📦 Assembly Tasks
| Task | What the robot must do |
|------|-----------------------|
| **Busbar assembly** | Grasp a long, heavy busbar, transport it to the tray, insert it, and screw it in at 16 locations. Fixtures and clamps must also be inserted and removed. |
| **Multi‑connector insertion** | Lift two large and two small cable‑mounted electrical connectors from the tray and insert them into tight‑clearance sockets. |

- These two tasks are the only critical steps identified by the NVIDIA Operations Team and Foxconn, the GB300 contract manufacturer.
- Skilled factory workers currently perform these tasks reliably and fluidly, without significant mental load.

## ⚙️ Key Challenges
- **Uncertainty** – Part geometry, appearance, and dynamics are not precisely known; initial poses can vary substantially.
- Connectors are attached to cables that deform along their entire length, exhibit manufacturing variation, and change mechanically through plastic deformation and fatigue.
- Rapid design cycles and low volumes make fixed automation infeasible, requiring flexible, adaptive robots.
- Manufacturers demand a **99.5 % success rate** and a cycle time **no longer than 124 seconds** (no more than twice the time of skilled workers). No unintended collisions with the tray are allowed.

## 🛠️ Technical Approach
- The team began with a **classical pipeline** of separate perception, planning, and control modules, expecting a later pivot to end‑to‑end learning.
- The classical pipeline proved **highly effective**, so no pivot was needed.
- For each sub‑problem the team:
  1. Implemented classical baselines first.
  2. When baselines fell short, explored:
     - Imitation learning
     - Simulation‑based reinforcement learning with sim‑to‑real transfer
     - Real‑world reinforcement learning
     - Vision‑language‑action (VLA) models
- This progression allowed the team to identify the strengths and weaknesses of each approach and justify added complexity.
- Initial conditions for busbar assembly matched the manufacturing setting: the limit fixture, busbar (with attached clamp), and screws were placed unconstrained on a flat surface next to the robot.

## 📈 Progress & Metrics
- In robotics research, 50‑60 % success rates are often sufficient, and 80‑90 % can be enough to call a task solved. 
- The performance requirements for GB300 tray assembly were set in direct collaboration with the NVIDIA Operations Team and Foxconn to ensure that “solved” truly means meeting the 99.5 % success and ≤124 seconds targets.
- As of the publication date, the system is **rapidly approaching** those thresholds.

## 💡 Why it matters
- Demonstrates that **adaptive, uncertainty‑aware robotics** can meet industrial‑grade quality and speed requirements for high‑value AI hardware.
- Shows that a well‑chosen classical engineering pipeline can succeed without immediate recourse to end‑to‑end learning, informing future robot‑automation projects.
- Provides a concrete path for deploying robots in low‑volume, high‑precision manufacturing environments where fixed automation is impractical.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image20.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-5-combined-1.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/connector-nurec.gif)

#NVIDIA #Robotics #Automation #AIHardware

---

*Source: [The Machines that Make the Machines | NVIDIA Technical Blog](https://developer.nvidia.com/blog/the-machines-that-make-the-machines/)*
