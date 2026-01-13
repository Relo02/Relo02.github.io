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
---

{{< notebook src="final_version.ipynb" >}}

## Problem

Autonomous pain classification in time-series data requires robust temporal modeling that can capture both short-term fluctuations and long-term dependencies from 30 joint measurements and 4 pain survey responses.

## Approach

- Implemented **Hybrid CNN-RNN architecture** with GRU layers for temporal pattern extraction
- Applied **sliding window technique** (size=10, stride=2) for sequence generation
- Integrated **attention mechanism** for weighted pooling over time steps
- Used **embedding layers** for categorical features (prosthetics, pain surveys)
- Applied **multi-level regularization**: L1/L2 penalties, dropout (0.4-0.6), early stopping

## Key Results

- Optimal architecture: **3-layer bidirectional GRU** with 64 hidden units
- GRU balanced performance and efficiency (25% fewer parameters than LSTM)
- Weighted F1 score as primary metric handling class imbalance
- Early stopping typically triggered at 50-150 epochs

## Technologies

- **Framework:** PyTorch with CUDA acceleration
- **Libraries:** NumPy, Pandas, Scikit-learn
- **Techniques:** CNN, RNN, LSTM, GRU, Attention, Time Series Windowing
- **Optimization:** Adam optimizer, ReduceLROnPlateau scheduling

## Implementation Highlights

### Architecture

```python
EnhancedSequenceClassifier(
    continuous_input_size=29,
    hidden_size=64,
    num_layers=3,
    rnn_type='GRU',
    bidirectional=True,
    dropout=0.4
)