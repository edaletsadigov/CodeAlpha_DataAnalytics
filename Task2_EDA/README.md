# Task 2 — Exploratory Data Analysis (EDA)

## Objective
Explore the scraped books dataset to uncover structure, distributions, anomalies, and relationships between variables before any modelling.

## Tools & Libraries
| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, cleaning, aggregation |
| `matplotlib` | Chart rendering |
| `seaborn` | Statistical visualization |

## Dataset
**Source:** `books_data.csv` (output of Task 1)

| Property | Value |
|----------|-------|
| Rows | 1,000 |
| Columns | 4 (title, price_gbp, rating, availability) |
| Null values | 0 |
| Duplicates | 0 |

## EDA Sections

### Section 1 — Structure & Data Types
- Shape, column names, dtypes confirmed
- All columns correctly typed (float, int, object)

### Section 2 — Missing Values & Duplicates
- Zero nulls across all columns
- Zero duplicate rows — dataset is clean

### Section 3 — Descriptive Statistics

| Metric | Price (£) | Rating |
|--------|-----------|--------|
| Mean | 35.07 | 2.92 |
| Median | 35.98 | 3.00 |
| Std Dev | 14.45 | 1.43 |
| Min | 10.00 | 1 |
| Max | 59.99 | 5 |

### Section 4 — Rating Distribution
- Distribution is **nearly uniform** across 1–5 stars
- 1★: 226 · 2★: 196 · 3★: 203 · 4★: 179 · 5★: 196
- No platform bias toward high ratings

### Section 5 — Price Distribution
- Spread: £10 – £60 with no extreme outliers
- Mean (£35.07) ≈ Median (£35.98) → roughly symmetric distribution

### Section 6 — Price by Rating
- **Pearson r = 0.028** → near-zero correlation
- Higher star rating does NOT predict higher price
- ⚠ Correlation ≠ causation — genre, publisher, and demand independently affect both

### Section 7 — Availability
- All 1,000 books are **In Stock**
- No stock-out cases in this dataset

## Output Charts

| File | Description |
|------|-------------|
| `chart_rating_distribution.png` | Bar + pie chart of star ratings |
| `chart_price_distribution.png` | Histogram + boxplot of prices |
| `chart_price_by_rating.png` | Boxplot: price grouped by rating |
| `chart_availability.png` | Bar chart of stock status |

## How to Run
1. Upload `task2_eda.ipynb` and `books_data.csv` to Google Colab
2. Run all cells sequentially
3. Charts auto-save as PNG files in the session

---
*CodeAlpha Data Analytics Internship · Task 2 of 4*

