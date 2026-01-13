---
title: Time Series Classification for Pain Detection
date: 2024-01-15
draft: false
summary: Deep learning approach for classifying pain levels in temporal data using hybrid CNN-RNN architecture with attention mechanisms
tags:
  - Deep Learning
  - Time Series
  - PyTorch
  - RNN
links:
  - type: code
    url: https://github.com/Relo02/Artificial-neural-networks-and-deep-learning-/blob/main/final_version.ipynb
    label: Source Code
---

## Problem

Autonomous pain classification in time-series data requires robust temporal modeling that can capture both short-term fluctuations and long-term dependencies from 30 joint measurements and 4 pain survey responses.

## Architecture

### High-Level Overview

```mermaid
flowchart TB
    subgraph Input["📥 Input Layer"]
        A[Raw Time Series Data<br/>30 Joints + 4 Surveys + Prosthetics]
    end
    
    subgraph Preprocessing["⚙️ Preprocessing"]
        B[Sliding Window<br/>size=10, stride=2]
        C[Feature Separation]
    end
    
    subgraph Features["🔀 Feature Processing"]
        D[Continuous Features<br/>29 Joint Values]
        E[Categorical Features<br/>Surveys + Prosthetics]
    end
    
    subgraph Encoders["🧠 Feature Encoders"]
        F[1D CNN Layers<br/>64 filters, kernel=3]
        G[Embedding Layers<br/>8-dim surveys, 4-dim prosthetics]
    end
    
    subgraph Temporal["⏱️ Temporal Processing"]
        H[Concatenate Features]
        I[3-Layer Bidirectional GRU<br/>hidden=64, dropout=0.4]
    end
    
    subgraph Attention["🎯 Attention Mechanism"]
        J[Learnable Attention Weights]
        K[Context Vector]
    end
    
    subgraph Output["📤 Output Layer"]
        L[Fully Connected Layers]
        M[Softmax<br/>3 Classes: No/Low/High Pain]
    end
    
    A --> B --> C
    C --> D & E
    D --> F
    E --> G
    F & G --> H --> I --> J --> K --> L -->M
```