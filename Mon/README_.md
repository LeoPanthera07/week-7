# Week 07 – Day 37 (Monday): NLP Foundations – TF-IDF

## Assignment
Q1: Implement TF-IDF from scratch on ShopSense reviews (10K rows), rank with cosine similarity, compare with sklearn.
Q2: Manual step-by-step TF-IDF calculation for 'fabric' in Clothing reviews, IDF comparison, BM25 bonus.

## Dataset
- `shopsense_reviews-2.csv` – 10K reviews (review_id, category, review_text, ...)
- `shopsense_customers-3.csv` – 100K customers (not used in today's tasks)

## How to run

1. Install dependencies:
```bash
pip install numpy pandas scipy scikit-learn
```

2. Place datasets in the same folder as the notebooks.

3. Run Q1:
```bash
jupyter notebook Q1_TFIDF_FromScratch.ipynb
```

4. Run Q2:
```bash
jupyter notebook Q2_TFIDF_HandCalc.ipynb
```

## Expected output
- Q1: TF-IDF sparse matrix (10K × vocab), top-5 cosine-ranked reviews for query, avg L2 vs sklearn, top Electronics word.
- Q2: Step-by-step TF/IDF/TF-IDF for 'fabric', IDF comparison for 'the' vs 'embroidery', 3-sentence rebuttal, BM25 top-5.

## Files
| File | Purpose |
|------|---------|
| Q1_TFIDF_FromScratch.ipynb | TF-IDF from scratch, retrieval, sklearn comparison |
| Q2_TFIDF_HandCalc.ipynb | Manual computation + verification + BM25 |
| Day37_Logic.md | Session logic and explanations |
| README.md | This file |
