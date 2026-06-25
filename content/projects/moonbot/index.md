---
title: MoonBot — YC Robotics Hackathon (w/ Innate)
date: 2026-05-01
summary: An edge-first autonomous robot for inspection & intervention in space-like environments. AprilTag localization plus an ACT imitation policy mapping perception directly to action.
tags:
  - Embodied AI
  - Imitation Learning
  - ACT
  - Perception
links:
  - type: custom
    name: Innate
    url: https://innate.bot
weight: 3
---

Built **MoonBot** (with R. Feingold, G. Voss, L. Knak, N. Rodriguez) at the **Y Combinator Robotics
Hackathon** — sponsored by NASA, DeepMind, Scale AI, Nebius, ElevenLabs, Dryft, and Iterate.

<!--more-->

An autonomous robot for **inspection / intervention in space-like environments** under a fully
embedded, **edge-first architecture** (no cloud, no external compute).

- **Perception:** AprilTag-based target localization from camera feeds.
- **Interaction:** once a target is reached, an **ACT (Action Chunking Transformer)** policy trained
  by imitation learning maps perception directly to action.
- **Navigation/control** designed to be robust to partial observability.

`Python` · `PyTorch` · `OpenCV` · `ROS 2`
