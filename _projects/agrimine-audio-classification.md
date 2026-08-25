---
layout: page
title: "Agricultural Sound Classification"
description: "CNN-14 and EfficientNet-B0 with multi-resolution Log-Mel spectrograms for agricultural bioacoustic audio classification — AgriMine 2025."
importance: 7
category: ml
tags: [Python, PyTorch, EfficientNet, CNN-14, Audio Classification]
github: https://github.com/aldennabil/agrimine-audio-classification
status: complete
year: 2025
competition:
  name: "AgriMine 2025 (Kaggle)"
---

## Overview

Acoustic monitoring in agricultural ecosystems enables automated detection of equipment anomalies, animal health status, and crop field conditions without invasive physical sensors.

This project built a deep learning bioacoustic classification pipeline for the **AgriMine 2025** competition, processing raw audio waveform signals into 2D time-frequency representations for vision-based neural networks.

---

## Signal Processing & Modeling Pipeline

1. **Audio Preprocessing & Augmentation**:
   - Resampled audio streams to 32 kHz with Log-Mel Spectrogram extraction (128 Mel bands, hop length 512).
   - Applied SpecAugment (time masking, frequency masking) and Mixup augmentations to prevent overfitting on ambient background noise.
2. **Deep Learning Backbones**:
   - **CNN-14 (PANNs architecture)**: Pretrained on AudioSet for general audio feature extraction.
   - **EfficientNet-B0**: Lightweight convolutional neural network fine-tuned on multi-resolution spectrograms.

---

## Performance Summary

| Architecture | Macro F1 | Accuracy | Inference Latency (CPU) |
|---|---|---|---|
| Random Forest + MFCC Baseline | 0.61 | 64.2% | 12 ms |
| EfficientNet-B0 (Spectrogram) | 0.81 | 82.7% | 45 ms |
| **CNN-14 Ensemble** | **0.87** | **88.4%** | **78 ms** |
