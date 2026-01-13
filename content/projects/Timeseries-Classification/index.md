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
    F & G --> H --> I --> J --> K --> L --> M

flowchart LR
    subgraph CNN["1D Convolutional Block"]
        direction TB
        C1[Conv1D<br/>in=29, out=64, k=3]
        C2[BatchNorm1D]
        C3[ReLU]
        C4[Dropout 0.6]
        C1 --> C2 --> C3 --> C4
    end
    
    subgraph EMB["Embedding Block"]
        direction TB
        E1[Survey Embeddings<br/>4 × 8-dim]
        E2[Prosthetic Embeddings<br/>3 × 4-dim]
        E3[Flatten & Concat]
        E1 & E2 --> E3
    end
    
    subgraph RNN["Recurrent Block"]
        direction TB
        R1[GRU Layer 1<br/>64 → 128 bidirectional]
        R2[GRU Layer 2<br/>128 → 128]
        R3[GRU Layer 3<br/>128 → 128]
        R4[Dropout 0.4]
        R1 --> R2 --> R3 --> R4
    end
    
    subgraph ATT["Attention Block"]
        direction TB
        A1[Linear → Tanh]
        A2[Linear → Softmax]
        A3[Weighted Sum]
        A1 --> A2 --> A3
    end
    
    subgraph FC["Classification Head"]
        direction TB
        F1[Linear 128 → 64]
        F2[ReLU + Dropout]
        F3[Linear 64 → 3]
        F4[Softmax]
        F1 --> F2 --> F3 --> F4
    end
    
    CNN --> RNN
    EMB --> RNN
    RNN --> ATT --> FC

flowchart TD
    subgraph DataPipeline["📊 Data Pipeline"]
        D1[(Raw CSV Data)]
        D2[Train/Val Split<br/>Pirate-level, 84/16]
        D3[StandardScaler<br/>fit on train only]
        D4[Sequence Builder<br/>window=10, stride=2]
        D5[DataLoader<br/>batch=256, shuffle]
        
        D1 --> D2 --> D3 --> D4 --> D5
    end
    
    subgraph Training["🏋️ Training Loop"]
        T1[Forward Pass]
        T2[Cross-Entropy Loss]
        T3[L1/L2 Regularization]
        T4[Backward Pass]
        T5[Adam Optimizer<br/>lr=0.003]
        T6[LR Scheduler<br/>ReduceOnPlateau]
        
        T1 --> T2 --> T3 --> T4 --> T5 --> T6
    end
    
    subgraph Monitoring["📈 Monitoring"]
        M1[Validation F1 Score]
        M2[Early Stopping<br/>patience=50]
        M3[Best Model Checkpoint]
        
        M1 --> M2 --> M3
    end
    
    D5 --> T1
    T6 --> M1