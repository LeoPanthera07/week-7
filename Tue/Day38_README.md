# Week 07 – Day 38 (Tuesday): Word Embeddings & Semantic Similarity

## Assignment
Q1: Train Word2Vec on ShopSense reviews. Explore polysemy of 'cheap', build context disambiguation, compare window sizes.
Q2: Compute cosine similarity between two semantically similar reviews using BOW, TF-IDF, Word2Vec averaging, and Sentence-BERT.

## Dataset
- `shopsense_reviews-2.csv` — 10K product reviews

## Dependencies
```bash
pip install numpy pandas gensim scikit-learn sentence-transformers
```

> sentence-transformers is only required for the SBERT cell in Q2.
> All other cells run without it.

## How to run

```bash
jupyter notebook Q1_Word2Vec_Polysemy.ipynb
jupyter notebook Q2_Similarity_BOW_TFIDF_W2V_SBERT.ipynb
```

## Expected output

### Q1
- Word2Vec vocab size (~5K–15K words)
- Single vector shape `(100,)` for 'cheap'
- `cosine('cheap','affordable')` and `cosine('cheap','flimsy')` printed
- Disambiguation result for 4 test sentences
- Nearest neighbours comparison for window=2 vs window=10

### Q2
- BOW cosine score (~0.0–0.15)
- TF-IDF cosine score (~0.0–0.15)
- Word2Vec avg cosine score (~0.30–0.60)
- SBERT cosine score (~0.70–0.85)
- Semantic gap explanation printed in the final cell

## Files
| File | Purpose |
|------|---------|
| Q1_Word2Vec_Polysemy.ipynb | Word2Vec training, polysemy demo, disambiguation, window comparison |
| Q2_Similarity_BOW_TFIDF_W2V_SBERT.ipynb | Four-method similarity comparison |
| Day38_Logic.md | Session logic and explanations |
| README.md | This file |
