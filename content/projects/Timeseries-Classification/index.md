---
title: Time Series Classification for Pain Detection
date: 2024-01-15
draft: false
summary: Deep learning approach for classifying pain levels in temporal data
  using hybrid CNN-RNN architecture with attention mechanisms
tags:
  - Deep Learning
  - Time Series
  - PyTorch
  - RNN
  - Jupyter
links:
  - type: code
    url: https://github.com/Relo02/Artificial-neural-networks-and-deep-learning-/blob/main/final_version.ipynb
    label: Source Code

---

## Problem

Autonomous pain classification in time-series data requires robust temporal modeling that can capture both short-term fluctuations and long-term dependencies from 30 joint measurements and 4 pain survey responses.

## Architecture

### Network Overview

```mermaid
flowchart TD
    subgraph Input
        I1[Time Series Input]
        I2[30 Joint Measurements]
        I3[4 Pain Surveys]
        I4[3 Prosthetic Features]
    end

    subgraph Preprocessing
        P1[Sliding Window]
        P2[Window Size: 10]
        P3[Stride: 2]
    end

    subgraph FeatureSplit
        F1[Continuous Features]
        F2[Categorical Features]
    end

    subgraph Encoders
        E1[1D Conv Layer]
        E2[BatchNorm + ReLU]
        E3[Dropout 0.6]
        E4[Embedding Layers]
    end

    subgraph RNN
        R1[GRU Layer 1]
        R2[GRU Layer 2]
        R3[GRU Layer 3]
        R4[Hidden: 64]
        R5[Dropout: 0.4]
    end

    subgraph Attention
        A1[Attention Weights]
        A2[Context Vector]
    end

    subgraph Output
        O1[FC Layer]
        O2[Softmax]
        O3[3 Classes]
    end

    I1 --> P1
    I2 --> P1
    I3 --> P1
    I4 --> P1
    P1 --> P2
    P2 --> P3
    P3 --> FeatureSplit
    F1 --> E1
    E1 --> E2
    E2 --> E3
    F2 --> E4
    E3 --> R1
    E4 --> R1
    R1 --> R2
    R2 --> R3
    R3 --> R4
    R4 --> R5
    R5 --> A1
    A1 --> A2
    A2 --> O1
    O1 --> O2
    O2 --> O3