---
title: Histopathology Image Classification — 4th / 170
date: 2025-12-01
summary: Transfer learning with a RetCCL-pretrained ResNet-50 for molecular-structure classification in tissue images. Ranked 4th of 170 teams on a hidden test set.
tags:
  - Deep Learning
  - Transfer Learning
  - PyTorch
  - Computer Vision
weight: 5
---

Image classification of molecular structures in tissue images for the **Artificial Neural Networks
& Deep Learning** course at Politecnico di Milano — **ranked 4th of 170 teams** on a hidden test set.

<!--more-->

- **Backbone:** transfer learning with a **ResNet-50** pre-trained via **RetCCL** for
  histopathology-specific feature extraction.
- **Pipeline:** reproducible **PyTorch Lightning** training with **WeightedRandomSampler** for class
  imbalance, **AdamW**, label smoothing, cosine annealing, and rotation/flip/color-jitter augmentation.

`Python` · `PyTorch` · `PyTorch Lightning` · `CNNs`
