---
title: "Bayesian Optimization for Learning Nonlinear MPC in Autonomous Agent Navigation"
authors:
- me
- G. Voss
- G. Beltrami
- F. Dorati
- T. F. Banfi
date: "2026-01-01T00:00:00Z"
publishDate: "2026-01-01T00:00:00Z"

# Publication type (CSL standard)
publication_types: ["paper-conference"]

publication: "IEEE ICRA 2026 Workshop"
publication_short: "ICRA 2026 Workshop"

abstract: We present a data-efficient framework that learns the cost weights of a nonlinear Model Predictive Control (MPC) navigation stack using Bayesian Optimization. Rather than hand-tuning the controller, we treat closed-loop navigation performance as a black-box objective and optimize the MPC parameters directly from rollouts, balancing tracking accuracy, safety, and smoothness. The approach is validated on an autonomous agent navigation task and deployed on a Unitree Go2 quadruped, yielding robust, generalizable behavior with far fewer trials than grid or manual tuning.

summary: A data-efficient framework that learns nonlinear MPC cost weights via Bayesian Optimization for autonomous agent navigation, deployed on a Unitree Go2 quadruped.

tags:
- Autonomous Agent Navigation
- Model Predictive Control
- Bayesian Optimization
- Legged Robotics
- Machine Learning

featured: true

hugoblox:
  ids:
    arxiv: "2606.14763"

links:
- type: preprint
  provider: arxiv
  id: "2606.14763"
- type: code
  url: https://github.com/talos-robotics-ai/Go2_navigation
- type: custom
  label: arXiv
  url: https://arxiv.org/abs/2606.14763

image:
  caption: ''
  focal_point: ""
  preview_only: false

projects: []
slides: ""
---

First-author work (with G. Voss, G. Beltrami, F. Dorati, and T. F. Banfi) presented at the
**IEEE ICRA 2026 Workshop**. We learn the weights of a nonlinear MPC navigation controller via
**Bayesian Optimization**, treating closed-loop performance as a black-box objective and deploying
the result on a **Unitree Go2** quadruped.

- 📄 [Read on arXiv](https://arxiv.org/abs/2606.14763)
- 💻 [Code on GitHub](https://github.com/talos-robotics-ai/Go2_navigation)
