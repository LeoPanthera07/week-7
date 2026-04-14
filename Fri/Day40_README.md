# Week 07 – Day 40 (Friday): Review Intelligence Synthesis

## Assignment
Sub‑steps 1–7 of the Week 07 Friday daily assignment:
- Understand label imbalance and why accuracy is misleading.
- Evaluate at least one sentiment classifier with class‑aware metrics.
- Compare two approaches under production constraints.
- Build a cost model and compute daily misclassification cost.
- Make a production recommendation and monitoring plan.
- Reproduce a broken 94%‑accuracy pipeline and fix it.
- Compare costs of the broken vs recommended pipelines.

## Dataset
- `product_reviews.csv` (ShopSense reviews) — provided on LMS checkpoint.

Place this file in the same `week-07/friday/` folder as the notebook.

## Environment

Python 3.9+ with:

```bash
pip install numpy pandas scikit-learn
```

## How to run

```bash
cd week-07/friday/

jupyter notebook Day40_ReviewIntelligence.ipynb
```

Run all cells in order. The notebook will:
- Load `product_reviews.csv`.
- Train a TF‑IDF + Logistic Regression baseline and a TF‑IDF + Linear SVM model.
- Print label distribution, per‑class metrics, confusion matrices, latency, and cost estimates.

## Expected outputs (high level)

- Table of sentiment label counts and percentages.
- Majority‑class baseline accuracy printed for comparison.
- Classification report and per‑class precision/recall/F1 for the baseline model.
- Macro F1 scores for code‑mixed and held‑out category subsets (if those columns exist).
- Latency per review in ms for both models.
- Daily misclassification cost estimates for each model and for the broken baseline.
- A one‑page technical brief for Priya in markdown form inside the notebook.

## Files

| File | Purpose |
|------|---------|
| Day40_ReviewIntelligence.ipynb | Full pipeline for sub‑steps 1–7 |
| Day40_Logic.md | Logic and explanations for the design |
