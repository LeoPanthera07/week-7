# Week 07 – Day 39 (Wednesday): Hard NLP Patterns & Aspect Sentiment

## Assignment
Q1: Build a pipeline for 5 challenging NLP patterns in Indian e-commerce reviews (negation, sarcasm, code-mixing, implicit, comparative).
Q2: Aspect-level sentiment analysis — why it is harder, how to improve it, and extracting aspect-sentiment pairs.

## Dataset
- `shopsense_reviews-2.csv` – 10K reviews

## Dependencies

```bash
pip install pandas vaderSentiment
```

## How to run

```bash
jupyter notebook Q1_HardNLP_Patterns.ipynb
jupyter notebook Q2_AspectSentiment.ipynb
```

## Expected output

### Q1
- Per pattern: input text, processed text, baseline VADER prediction, and a printed explanation of the failure mode
- Full pipeline applied to 5 real ShopSense reviews with active pattern detection flags

### Q2
- Printed explanation of why aspect-level is harder (5 reasons)
- Improvement plan (5 strategies to reach 80%+)
- Aspect-sentiment pairs for the target review: camera=Positive, battery=Negative, customer_support=Negative
- Aspect extraction on 10 real reviews showing multi-aspect outputs

## Files
| File | Purpose |
|------|---------|
| Q1_HardNLP_Patterns.ipynb | 5 hard NLP pattern handlers + full pipeline |
| Q2_AspectSentiment.ipynb | Aspect-level analysis + pair extraction |
| Day39_Logic.md | Session logic and explanations |
| README.md | This file |
