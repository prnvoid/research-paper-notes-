# BERT4Rec

## Paper
https://arxiv.org/abs/1904.06690

## Problem

Sequential recommendation systems only use past interactions.

## Key Idea

Use Transformer encoder with masked item prediction.

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
