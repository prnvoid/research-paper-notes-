# BERT4Rec

## Paper
[BERT4Rec Paper](https://arxiv.org/abs/1904.06690)

## Problem Statement

Unidirectional recommendation systems are insufficient in learning dynamic behavior sequences.

## Key Idea

- Use Transformer encoder with masked item prediction,i.e. ,  learns context from both directions and fills in masks.

## Key Concepts

### Cloze Task

BERT4Rec adapts the Cloze task from Natural Language Processing.

The Cloze task involves masking part of a sequence and predicting the missing element from the surrounding context in NLP and this context as well.

Example in Recommendation:

Radiohead → [MASK] → Slowdive

Prediction:
MBV

### Transformer Encoder

The model uses the Transformer encoder architecture rather than RNNs.

Advantages:
- Parallel computation
- Better long-range dependency modeling

### Self-Attention

Self-attention allows every item in a sequence to interact with every
other item.

This helps in identifying relationships between distant items.

## Dataset

- MovieLens 1M
- Steam

## Strengths

- Bidirectional context
- Strong performance

## Weaknesses

- Requires user interaction history
- Computationally expensive

## My Takeaways

1. Could be useful for music recommendation.
2. Requires listening sequence data.
3. Hard to apply directly to FMA dataset.

## Ideas For My Project

Compare:
- Cosine Similarity
- BERT4Rec

Measure:
- Precision@K
- Novelty
- Diversity
