# Week 07 – Monday: NLP Foundations / TF-IDF

## What is in this folder

| File | Description |
|---|---|
| `Q1_TFIDF_Scratch.ipynb` | TF-IDF from scratch on 10K ShopSense reviews |
| `Q2_TFIDF_Manual.ipynb` | Manual TF-IDF computation + BM25 bonus for Clothing reviews |
| `Day37_PM_Logic.md` | Session logic and design decisions |

## Dependencies

```
pip install numpy pandas scipy scikit-learn
```

## How to run

1. Place `shopsense_reviews-2.csv` in the same folder.
2. Run `Q1_TFIDF_Scratch.ipynb` first (builds vocabulary and TF-IDF matrix).
3. Run `Q2_TFIDF_Manual.ipynb` for manual arithmetic and BM25.

## Expected outputs

- Q1: TF-IDF sparse matrix (10K × vocab_size), top-5 query results, avg L2 vs sklearn, top Electronics word.
- Q2: Printed step-by-step TF/IDF/TF-IDF values, BM25 vs TF-IDF score comparison.
