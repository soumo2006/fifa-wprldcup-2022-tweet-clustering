
# FIFA World Cup 2022 — Opening Day Twitter Topic Discovery

Unsupervised topic discovery on FIFA World Cup 2022 opening-day tweets using 
TF-IDF vectorization and K-Means clustering, with sentiment and engagement 
analysis layered on top.

## 📌 Project Overview

Rather than predicting labels, this project asks: **what were people actually 
talking about during the World Cup 2022 opening day, and how did sentiment vary 
by topic?** Using unsupervised K-Means clustering on TF-IDF vectors of ~20,000 
cleaned tweets, six distinct discussion themes emerged.

*Note on scope:* the dataset covers only the tournament's opening day 
(Nov 20, 2022 — Qatar vs Ecuador). Findings reflect Day 1 discourse, not the 
full tournament.

## 🔍 Key Findings

- *General World Cup commentary* (71.4%) was the dominant theme — broad match 
  reactions, banter, and live updates
- *Opening ceremony & tournament kickoff* content made up ~15% of discussion
- A distinct cluster captured *political/social commentary*, including 
  human-rights-related tweets tied to the Iran national team's participation — 
  a real-world pattern reflected directly in the data
- Sentiment varied meaningfully across topics (see notebook for full breakdown)

## 🛠️ Methodology

1. *Data*: [FIFA World Cup 2022 Tweets](https://www.kaggle.com/datasets/tirendazacademy/fifa-world-cup-2022-tweets) 
   (Kaggle, ~30K tweets, pre-tagged sentiment via RoBERTa)
2. *Cleaning*: removed URLs, mentions, hashtags, non-ASCII/emoji bytes; 
   deduplicated near-identical tweets
3. *Vectorization*: TF-IDF (1000 features, English stopwords, min_df=5, max_df=0.8)
4. *Clustering*: K-Means, K selected via elbow method (K=6)
5. *Validation*: manual inspection of top keywords + sample tweets per cluster
6. *Analysis*: topic popularity (volume + engagement), sentiment breakdown per topic

## 📊 Tech Stack

pandas · scikit-learn (TF-IDF, KMeans, PCA) · matplotlib

## 📁 Contents

- wc2022_tweet_clustering.ipynb — full analysis notebook

## 🚀 Possible Extensions

- Apply the same pipeline to a full-tournament dataset for broader topic coverage
- Compare against live Reddit discussion for World Cup 2026
- Increase K to further split the dominant "general commentary" cluster

---
Built as part of an ongoing data science portfolio.
