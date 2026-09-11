# Music Discovery Patterns

## Paper

[Familiarizing with Music: Discovery Patterns for Different Music Discovery Needs](https://arxiv.org/abs/2505.03568)
(Moscati, Afchar, Schedl & Sguerra — UMAP '25)

## Problem Statement

Little is known about *how* users discover and explore previously unfamiliar music, and how this exploration behavior differs depending on a user's self-declared need for discovery. Prior work looked at diversity/novelty of consumption, but not the discovery *process* itself.

## Key Idea

- Combine a **user survey** (self-declared interest in discovering unfamiliar music) with **real Deezer streaming data** to study discovery patterns empirically, rather than inferring discovery need only from behavior.

## Key Concepts

### Discovery vs. Exploration

- **Discovery**: listening to a track/artist not previously listened to.
- Framed against the idea that music liking rises with familiarity, then peaks and declines — so a good recommender needs to balance familiar and unfamiliar content.

### Discovery Needs

- Users self-report their interest in unfamiliar music via survey (varying "discovery needs": low → high).
- This is treated as a trait to correlate against streaming behavior, rather than assumed from listening history alone.

### Track Cluster Labels

- Tracks are grouped into similarity clusters using **co-occurrence in user-generated playlists**, giving each track a cluster label used to measure genre/type representativeness of what users explore.

## Dataset

- Deezer (major music streaming platform)
- Survey responses + corresponding streaming histories

## Strengths

- Grounds "discovery need" in real self-reported data instead of a proxy
- Combines qualitative (survey) and behavioral (streaming logs) signals
- Identifies concrete, measurable patterns (popularity, genre representativeness) rather than only diversity metrics

## Weaknesses

- Survey-based labels rely on self-report accuracy (*Main*)
- Single platform (Deezer) — may not generalize to other services
- Correlational, not causal — doesn't test whether nudging discovery changes stated needs

## My Takeaways

1. Confirms that users with higher declared discovery interest do listen to more diverse music and explore more within the same time window.
2. When exploring, users don't pick unfamiliar tracks randomly — clear **popularity** and **genre representativeness** patterns emerge, and these patterns differ by discovery-need group.
3. Opens the door to *inferring* discovery need directly from streaming data (no survey required) — relevant for cold-start / implicit personalization.

## Ideas For My Project

Use inferred discovery-need signals (popularity/genre representativeness of newly played tracks) as an **auxiliary feature** alongside BERT4Rec sequence embeddings + audio content embeddings → hybrid recommender that adapts exploration/exploitation balance per user.

Measure:

- Precision@K
- Novelty
- Discovery-need-conditioned diversity (does the model over/under-explore for a given user segment?)
