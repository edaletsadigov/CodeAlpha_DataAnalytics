# Task 4 — Sentiment Analysis

## Objective
Analyze Amazon product reviews to classify customer sentiment as positive, negative, or neutral using NLP techniques and machine learning.

## Tools & Libraries
| Library | Purpose |
|---------|---------|
| `vaderSentiment` | Rule-based sentiment scoring |
| `textblob` | Polarity + subjectivity scoring |
| `scikit-learn` | TF-IDF vectorization + ML classifiers |
| `wordcloud` | Visual word frequency analysis |
| `pandas` | Data manipulation |
| `matplotlib / seaborn` | Visualization |

## Dataset
**Source:** [Amazon Fine Food Reviews](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews) (Kaggle)

| Property | Value |
|----------|-------|
| Full dataset | 568,454 reviews |
| Sample used | 10,000 (balanced — 2,000 per star rating) |
| Columns used | Score (1–5), Text, Summary |
| Null values | 0 (after cleaning) |

## Pipeline

### Stage 1 — Text Cleaning
- HTML tag removal
- URL removal
- Special character stripping
- Lowercasing
- Whitespace normalization

### Stage 2 — VADER Sentiment Scoring
Rule-based lexicon model optimized for social media and review text.

| Label | Count | Percentage |
|-------|-------|------------|
| Positive | 7,886 | 78.9% |
| Negative | 1,772 | 17.7% |
| Neutral | 342 | 3.4% |

**Threshold:** compound ≥ 0.05 → positive · ≤ −0.05 → negative · else → neutral

### Stage 3 — TextBlob Scoring
Lexicon-based polarity and subjectivity scoring.

| Label | Count | Percentage |
|-------|-------|------------|
| Positive | 7,176 | 71.8% |
| Neutral | 1,504 | 15.0% |
| Negative | 1,320 | 13.2% |

**VADER ↔ TextBlob Agreement: 74.5%**  
⚠ Agreement ≠ accuracy — both are unsupervised. Ground truth tested via ML below.

### Stage 4 — ML Classifier

**Setup:**
- Ground truth: star rating → positive (4–5★) / neutral (3★) / negative (1–2★)
- ML task: binary classification (positive vs negative, neutral removed)
- Train/test split: 80/20 stratified
- Features: TF-IDF (15,000 features, unigrams + bigrams, sublinear TF)

**Results:**

| Model | Test Accuracy | Notes |
|-------|--------------|-------|
| Logistic Regression | **83.8%** | 🏆 Best model |
| Random Forest | 78.6% | TF-IDF sparse matrix less suited for RF |

**Confusion Matrix (Logistic Regression):**
```
              Predicted Pos  Predicted Neg
Actual Pos         669            131
Actual Neg         129            671
```
Precision = 84% · Recall = 84% · F1 = 84% (both classes balanced)

## Output Charts

| File | Description |
|------|-------------|
| `sent1_vader_distribution.png` | VADER sentiment bar chart |
| `sent2_vader_vs_textblob.png` | Pie comparison: VADER vs TextBlob |
| `sent3_compound_distribution.png` | Compound score histogram by sentiment |
| `sent4_confusion_matrix.png` | ML confusion matrix |
| `sent5_polarity_subjectivity.png` | TextBlob scatter: polarity vs subjectivity |
| `sent6_wordcloud.png` | WordCloud: positive vs negative top words |
| `sent7_model_comparison.png` | LR vs RF accuracy bar chart |

## Key Findings
1. Amazon reviews are **strongly positive** — 78.9% classified as positive by VADER
2. VADER and TextBlob agree on **74.5%** of reviews — reasonable for two independent unsupervised methods
3. Logistic Regression with TF-IDF achieves **83.8% accuracy** on unseen reviews
4. Positive reviews use words like: *food, love, great, coffee, tea*
5. Negative reviews use words like: *bad, taste, disappointed, flavor, cup*
6. ⚠ Positive skew in Amazon reviews is well-documented — buyers who dislike products less often leave reviews

## How to Run
1. Download `Reviews.csv` from [Kaggle](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
2. Upload `task4_sentiment_analysis.ipynb` and `Reviews.csv` to Google Colab
3. Run cells sequentially (Cell 1 installs libraries — wait for completion)
4. Total runtime: ~8–12 minutes on Colab free tier

### Install Requirements
```python
!pip install vaderSentiment textblob wordcloud scikit-learn -q
```

---
*CodeAlpha Data Analytics Internship · Task 4 of 4*

