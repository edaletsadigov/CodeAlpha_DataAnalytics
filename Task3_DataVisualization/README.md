# Task 3 — Data Visualization

## Objective
Transform EDA findings into a professional, portfolio-ready visual story using diverse chart types. Each visualization answers a specific analytical question.

## Tools & Libraries
| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation |
| `matplotlib` | Core chart rendering, GridSpec dashboard |
| `seaborn` | Statistical charts (violin, boxplot) |
| `numpy` | Stacked bar percentage calculations |

## Dataset
**Source:** `books_data.csv` (1,000 books · 4 columns)

**Derived features created for visualization:**
- `price_bucket` — price grouped into £10 ranges (£0–20, £21–30, £31–40, £41–50, £51–60)
- `rating_label` — star labels with symbols (★, ★★, ...)

## Visualizations

### Chart 1 — Horizontal Bar: Book Count by Rating
**Question:** How are books distributed across star ratings?  
**Answer:** Nearly uniform — no bias toward 5-star books.  
**File:** `viz1_rating_bar.png`

### Chart 2 — KDE + Histogram: Price Distribution
**Question:** What does the price distribution look like?  
**Answer:** Symmetric spread £10–£60. Mean (£35.07) ≈ Median (£35.98).  
**File:** `viz2_price_kde.png`

### Chart 3 — Grouped Bar: Average Price per Rating
**Question:** Do higher-rated books cost more?  
**Answer:** No. All rating groups average ~£34–36. r = 0.028.  
**File:** `viz3_avg_price_rating.png`

### Chart 4 — Stacked Bar: Rating Composition by Price Bucket
**Question:** Do expensive books get better ratings?  
**Answer:** Rating mix is consistent across all price ranges — price does not predict rating.  
**File:** `viz4_rating_by_price_bucket.png`

### Chart 5 — Violin Plot: Price Spread by Rating
**Question:** Is price variance different for high-rated books?  
**Answer:** All rating groups show identical price spread — confirming no price-rating link.  
**File:** `viz5_violin_price_rating.png`

### Chart 6 — Dashboard (2×2 Grid)
**Content:** Rating bar · Price histogram · Avg price by rating · Price range donut  
**File:** `viz6_dashboard.png`

## Design Standards Applied
- Every chart: title + axis labels + takeaway annotation
- Consistent color palette across all charts
- Top/right spines removed for clean look
- All charts saved at 150 DPI (high resolution)

## Key Analytical Story
> Books priced at £10 and £60 are equally likely to receive 1 star or 5 stars.  
> Price is not a signal of quality on this platform.  
> ⚠ This is observational — correlation ≠ causation.

## How to Run
1. Upload `task3_visualization.ipynb` and `books_data.csv` to Google Colab
2. Run all cells sequentially
3. All 6 PNG files auto-save to the session

---
*CodeAlpha Data Analytics Internship · Task 3 of 4*

