# 🎵 Hybrid Music Recommendation System

> A research-oriented music recommendation system that explores content-based and collaborative filtering techniques to improve the discovery of obscure and long-tail music using the Free Music Archive (FMA) dataset.

---

## 📌 Overview

Traditional music recommendation systems often prioritize popular songs because they rely heavily on user interaction data. This creates a **long-tail problem**, where thousands of high-quality but lesser-known tracks are rarely included in the recommendation mix.

This project aims to build a scalable recommendation engine capable of discovering these overlooked and underrated songs by combining metadata, audio features, and user listening behavior.

---

## 🎯 Objectives

* Recommend musically similar songs using metadata and audio features.
* Reduce popularity bias by improving recommendations for obscure tracks.
* Handle the cold-start problem for songs with little or no interaction history.
* An attempt at filling in on gaps already existing.

---

## 📚 Dataset

**Free Music Archive (FMA)**

The project uses the FMA dataset, a large open music dataset widely used in Music Information Retrieval (MIR) research.

Dataset includes:

* 106,574 tracks
* Independent and underground artists
* Genre metadata
* Artist and album metadata
* Audio features
* EchoNest metadata

Repository:
https://github.com/mdeff/fma

---

## 🛠️ Tech Stack

### Languages

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

### Dataset

* Free Music Archive (FMA)

---

## 🚀 Development Roadmap

### Phase 1 — Dataset Exploration

* [x] Load FMA metadata
* [x] Explore dataset structure
* [x] Clean metadata
* [x] Exploratory Data Analysis

### Phase 2 — Content-Based Recommendation

* [x] Feature engineering
* [ ] TF-IDF vectorization
* [ ] Cosine similarity
* [ ] Song recommendation pipeline

### Phase 3 — Audio-Based Recommendation

* [ ] Audio feature preprocessing
* [ ] Feature normalization
* [ ] Audio similarity retrieval

### Phase 4 — Collaborative Filtering

* [ ] User-item interaction matrix
* [ ] Matrix factorization (SVD)
* [ ] Recommendation evaluation

### Phase 5 — Hybrid Recommendation

* [ ] Combine content-based and collaborative models
* [ ] Cold-start handling
* [ ] Recommendation ranking

### Phase 6 — Deployment

* [ ] FastAPI REST API
* [ ] FAISS vector search
* [ ] Interactive demo

---



---

## 📈 Current Progress

Currently working on:

* Loading and understanding the FMA dataset
* Exploring metadata and audio features
* Preparing data for the first content-based recommendation model

---

## 🔮 Future Improvements

* Transformer-based music embeddings
* Deep learning audio representations
* User clustering
* Session-aware recommendations
* Spotify API integration
* Explainable recommendations

---

## 👨‍💻 Author

**Pranav R. Kumar**

Interests:

* Recommendation Systems
* Machine Learning
* Music Information Retrieval
* Representation Learning
* Human-Centered AI
