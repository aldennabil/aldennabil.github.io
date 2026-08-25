---
layout: page
title: "Coffee Wars: WFC vs Lifestyle Market Positioning via MDS & NLP"
description: "Google Maps reviews scraping, TextBlob sentiment scoring, and 2D Multidimensional Scaling perceptual mapping for coffee shop competitive strategy in Bogor."
importance: 20
category: nlp
tags: [Python, Multidimensional Scaling, NLP, Sentiment Analysis, Google Maps Scraping]
github: https://github.com/aldennabil/bogor-coffeeshop-mds-sentiment
status: complete
year: 2024
---

## Overview

The coffee shop market in Bogor City has bifurcated into two primary consumer segments: **"Work-From-Cafe" (WFC)**—demanding reliable Wi-Fi, abundant power outlets, and ergonomic seating—and **"Lifestyle / Hangout"**—prioritizing visual aesthetics, outdoor social spaces, and specialty coffee varieties.

This project combined automated web scraping of Google Maps reviews, Natural Language Processing (NLP) sentiment scoring, and **Multidimensional Scaling (MDS)** to construct a competitive 2D perceptual brand map.

---

## Technical Pipeline

1. **Review Scraping & Preprocessing**:
   - Extracted 1,200+ consumer review texts and star ratings across 15 prominent coffee establishments in Bogor.
2. **NLP Sentiment & Aspect Extraction**:
   - Applied Indonesian stopwords removal, tokenization, and polarity scoring to isolate aspect-level sentiments (Ambiance, Connectivity, Product Quality, Price Value).
3. **Multidimensional Scaling (MDS)**:
   - Constructed a pairwise Euclidean dissimilarity matrix $D$ across sentiment and attribute vectors:
     $$\min_{X} \sum_{i < j} (d_{ij}(X) - \delta_{ij})^2$$
   - Projected establishments into a 2D perceptual space (Stress-1 value = 0.082, indicating good dimensional fit).

---

## Strategic Takeaways

- Identified a distinct market "white space" for hybrid coffee shops offering designated quiet zones with high-speed internet during weekday business hours, converting into social aesthetic spaces on weekends.
