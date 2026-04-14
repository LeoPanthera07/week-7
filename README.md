# Week 07 – NLP & Production Readiness

This repo contains all Week 07 daily assignments (Days 37–40) built on the ShopSense e‑commerce datasets.
The focus is on TF‑IDF, embeddings, sentiment analysis, hard NLP patterns, and production‑grade evaluation.

## Folder structure

```text
week07/
  monday/    # Day 37 – TF‑IDF foundations & BM25
  tuesday/   # Day 38 – Word2Vec & semantic similarity
  wednesday/ # Day 39 – Hard NLP patterns & aspect sentiment
  friday/    # Day 40 – Review intelligence & production evaluation
```

Each day has:
- 1–2 Jupyter notebooks solving the questions for that day.
- A logic `.md` file explaining design choices.
- A day‑level README (or equivalent) with run steps.

## Environment setup (common)

Recommended Python: **3.9+**

Install core dependencies:

```bash
pip install numpy pandas scikit-learn scipy gensim vaderSentiment sentence-transformers
```

> Some days use only a subset of these; installing all once keeps things simple.

You also need the ShopSense datasets provided on LMS:
- `shopsense_reviews.csv`
- `shopsense_customers.csv` (used mainly for reference / later days)

Place the required CSV files into the corresponding day folders as noted below.

---

## Day 37 – Monday (TF‑IDF Foundations)

**Folder:** `week07/monday/`

### Files
- `Q1_TFIDF_FromScratch.ipynb` – Full TF‑IDF implementation on 10K ShopSense reviews, cosine search, comparison with `TfidfVectorizer`.
- `Q2_TFIDF_HandCalc.ipynb` – Manual TF/IDF/TF‑IDF arithmetic for `fabric` + BM25 bonus.
- `Day37_Logic.md` – Explanations and design notes.

### Data
- Copy `shopsense_reviews.csv` into `week07/monday/`.

### How to run

```bash
cd week07/monday/
jupyter notebook Q1_TFIDF_FromScratch.ipynb
jupyter notebook Q2_TFIDF_HandCalc.ipynb
```

### Concepts
- Implementing TF‑IDF from scratch (sparse matrices, IDF smoothing).
- Query ranking with cosine similarity.
- Verifying scratch implementation against sklearn.
- Hand‑computed TF/IDF for specific words and BM25 scoring.

---

## Day 38 – Tuesday (Word2Vec & Semantic Similarity)

**Folder:** `week07/tuesday/`

### Files
- `Q1_Word2Vec.ipynb` – Train Word2Vec on ShopSense reviews, explore polysemy of `cheap`, build a sense disambiguation helper, compare window sizes.
- `Q2_SimilarityComparison.ipynb` – Compare BOW, TF‑IDF, Word2Vec averaging, and Sentence‑BERT on semantically similar reviews.
- `Day38_Logic.md` – Explanations and design notes.

### Data
- Copy `shopsense_reviews.csv` into `week07/tuesday/`.

### Extra dependencies

```bash
pip install gensim sentence-transformers
```

### How to run

```bash
cd week07/tuesday/
jupyter notebook Q1_Word2Vec.ipynb
jupyter notebook Q2_SimilarityComparison.ipynb
```

### Concepts
- Static word embeddings (Word2Vec) and polysemy (one vector per word).
- Using anchor vectors + context to disambiguate senses of `cheap`.
- Why BOW/TF‑IDF miss synonymy and paraphrase.
- How Word2Vec and Sentence‑BERT progressively close the semantic gap.

---

## Day 39 – Wednesday (Hard NLP Patterns & Aspect Sentiment)

**Folder:** `week07/wednesday/`

### Files
- `Q1_HardNLP_Patterns.ipynb` – Pipelines for:
  - Negation (`not bad at all`),
  - Sarcasm (`Wow great! Broke on day 1`),
  - Code‑mixing (Hindi/English),
  - Implicit sentiment (`Returned it within 2 hours`),
  - Comparative sentiment (`Way better than my previous Samsung`).
- `Q2_AspectSentiment.ipynb` – Aspect‑level vs review‑level sentiment, cost/benefit, and aspect‑sentiment pair extraction.
- `Day39_Logic.md` – Explanations and design notes.

### Data
- Copy `shopsense_reviews.csv` into `week07/wednesday/`.

### Extra dependencies

```bash
pip install vaderSentiment
```

### How to run

```bash
cd week07/wednesday/
jupyter notebook Q1_HardNLP_Patterns.ipynb
jupyter notebook Q2_AspectSentiment.ipynb
```

### Concepts
- Why off‑the‑shelf sentiment fails on negation, sarcasm, code‑mix, implicit and comparative language.
- Lightweight heuristics and feature engineering to catch these patterns.
- Difference between review‑level and aspect‑level F1.
- Extracting `(aspect, sentiment)` pairs from multi‑aspect reviews.

---

## Day 40 – Friday (Review Intelligence & Production Evaluation)

**Folder:** `week07/friday/`

### Files
- `Day40_ReviewIntelligence.ipynb` – Single end‑to‑end notebook implementing sub‑steps 1–7 from the Friday assignment.

### Data
- Copy `shopsense_reviews.csv` (LMS checkpoint version of ShopSense reviews) into `week07/friday/`.

### How to run

```bash
cd week07/friday/
jupyter notebook Day40_ReviewIntelligence.ipynb
```

### Concepts
- Class imbalance and why raw accuracy is misleading.
- Evaluating TF‑IDF + linear models with macro‑F1 and per‑class recall.
- Quantitative checks for:
  - new categories without retraining,
  - code‑mixed reviews,
  - < 20 ms inference latency.
- Cost model for false negatives vs false positives at 100k reviews/day.
- One‑page production recommendation + monitoring plan.
- Reproducing and fixing a broken 94%‑accuracy majority‑class pipeline.

---
