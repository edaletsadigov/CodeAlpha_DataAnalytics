# CodeAlpha_DataAnalytics
Internship Projects 

# CodeAlpha — Data Analytics Internship Projects

**Intern:** Ədalət  
**Organization:** CodeAlpha  
**Period:** 2026  
**Tools:** Python · pandas · matplotlib · seaborn · scikit-learn · BeautifulSoup · VADER · TextBlob

---

## Project Overview

This repository contains all 4 Data Analytics tasks completed during the CodeAlpha internship program. Each task is self-contained with its own dataset, code, and visual outputs.

| Task | Topic | Dataset | Key Output |
|------|-------|---------|------------|
| Task 1 | Web Scraping | books.toscrape.com | `books_data.csv` (1,000 books) |
| Task 2 | Exploratory Data Analysis | `books_data.csv` | 4 charts + statistical summary |
| Task 3 | Data Visualization | `books_data.csv` | 6 charts + dashboard |
| Task 4 | Sentiment Analysis | Amazon Fine Food Reviews | 7 charts · LR 83.8% accuracy |

---

## Repository Structure

```
CodeAlpha_DataAnalytics/
│
├── Task1_WebScraping/
│   ├── task1_web_scraping.ipynb
│   ├── books_data.csv
│   └── README.md
│
├── Task2_EDA/
│   ├── task2_eda.ipynb
│   ├── chart_rating_distribution.png
│   ├── chart_price_distribution.png
│   ├── chart_price_by_rating.png
│   ├── chart_availability.png
│   └── README.md
│
├── Task3_DataVisualization/
│   ├── task3_visualization.ipynb
│   ├── viz1_rating_bar.png
│   ├── viz2_price_kde.png
│   ├── viz3_avg_price_rating.png
│   ├── viz4_rating_by_price_bucket.png
│   ├── viz5_violin_price_rating.png
│   ├── viz6_dashboard.png
│   └── README.md
│
├── Task4_SentimentAnalysis/
│   ├── task4_sentiment_analysis.ipynb
│   ├── sentiment_results.csv
│   ├── sent1_vader_distribution.png
│   ├── sent2_vader_vs_textblob.png
│   ├── sent3_compound_distribution.png
│   ├── sent4_confusion_matrix.png
│   ├── sent5_polarity_subjectivity.png
│   ├── sent6_wordcloud.png
│   ├── sent7_model_comparison.png
│   └── README.md
│
└── README.md  ← (this file)
```

---

## Key Results Summary

### Task 1 — Web Scraping
- Scraped **1,000 books** across 50 pages from books.toscrape.com
- Extracted: title, price (£), star rating, availability
- Output: clean CSV with 0 null values, 0 duplicates

### Task 2 — EDA
- Price range: **£10.00 – £59.99** | Mean: £35.07 | Median: £35.98
- Rating distribution: **uniform** across 1–5 stars (no platform bias)
- Price–Rating correlation: **r = 0.028** (near-zero)
- All 1,000 books: **In Stock**

### Task 3 — Data Visualization
- 6 professional charts: horizontal bar, KDE histogram, grouped bar, stacked bar, violin plot, dashboard
- Key insight: price does **not** predict rating across any price bucket

### Task 4 — Sentiment Analysis
- Dataset: **10,000 Amazon Fine Food Reviews** (balanced, 2,000 per star)
- VADER: 78.9% positive · 17.7% negative · 3.4% neutral
- VADER ↔ TextBlob agreement: **74.5%**
- Logistic Regression accuracy: **83.8%** (best model)
- Random Forest accuracy: 78.6%

---

## How to Run

All notebooks are designed for **Google Colab**. No local setup required.

1. Open [colab.research.google.com](https://colab.research.google.com)
2. Upload the `.ipynb` file for the task you want to run
3. Upload the required dataset (if any) to the Colab session
4. Run all cells sequentially (Runtime → Run all)

### Dependencies

```python
# Task 1–3
pip install requests beautifulsoup4 pandas matplotlib seaborn

# Task 4 (additional)
pip install vaderSentiment textblob wordcloud scikit-learn
```

---

## Analytical Notes

- **Correlation ≠ causation** — all r values reported are observational only
- All ML models use stratified train/test split (80/20) with `random_state=42` for reproducibility
- No data leakage — preprocessing fitted on training set only
- Balanced sampling used in Task 4 to prevent class bias

---

*CodeAlpha Data Analytics Internship · 2026*
