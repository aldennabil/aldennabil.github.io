---
layout: page
title: "Skincare Product Sentiment Analysis"
description: "NLP sentiment analysis on Indonesian e-commerce consumer reviews comparing lexicon-based TextBlob with fine-tuned IndoBERT embeddings."
importance: 21
category: nlp
tags: [Python, NLP, TextBlob, IndoBERT, NLTK, Sentiment Analysis]
github: https://github.com/aldennabil/skincare-sentiment-nlp
status: complete
year: 2024
---

## Overview

Consumer feedback on e-commerce platforms provides rich signal for brand reputation management and product iteration. However, Indonesian text reviews frequently contain slang, typographical noise, and mixed-language expressions.

This project developed a Natural Language Processing (NLP) sentiment pipeline comparing rule-based dictionary models against contextual deep learning embeddings on skincare consumer reviews.

---

## Technical Pipeline

1. **Text Normalization for Indonesian Slang**:
   - Engineered custom dictionary token replacement for Indonesian informal abbreviations (e.g. `"bgt" -> "banget"`, `"ga ngefek" -> "tidak berpengaruh"`), emoji parsing, and noise elimination.
2. **Sentiment Modeling Approaches**:
   - **Lexicon Baseline**: TextBlob with translated polarity dictionaries.
   - **Transformer Architecture**: Fine-tuned **IndoBERT** (`indobert-base-p1`) with cross-entropy loss for 3-class sentiment classification (Positive, Neutral, Negative).

---

## Performance Summary

| Architecture | Precision | Recall | Macro F1-Score |
|---|---|---|---|
| Lexicon Baseline (TextBlob) | 0.64 | 0.58 | 0.61 |
| TF-IDF + Logistic Regression | 0.76 | 0.74 | 0.75 |
| **Fine-Tuned IndoBERT** | **0.89** | **0.88** | **0.88** |
