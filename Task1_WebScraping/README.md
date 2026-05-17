# Task 1 — Web Scraping

## Objective
Extract structured data from a public website using Python and save it as a clean, analysis-ready CSV file.

## Tools & Libraries
| Library | Purpose |
|---------|---------|
| `requests` | HTTP requests to fetch web pages |
| `BeautifulSoup` | HTML parsing and data extraction |
| `pandas` | Data structuring and CSV export |
| `time` | Polite delay between requests |

## Dataset
**Source:** [books.toscrape.com](https://books.toscrape.com) — a public sandbox website for web scraping practice.

| Property | Value |
|----------|-------|
| Pages scraped | 50 |
| Total records | 1,000 books |
| Columns | title, price_gbp, rating, availability |
| Null values | 0 |
| Duplicates | 0 |

## Output File
`books_data.csv`

| Column | Type | Description |
|--------|------|-------------|
| `title` | string | Full book title |
| `price_gbp` | float | Price in British Pounds (£) |
| `rating` | int | Star rating (1–5) |
| `availability` | string | Stock status |

## How to Run
1. Open Google Colab → New notebook
2. Upload `task1_web_scraping.ipynb`
3. Run all cells — no dataset upload needed (data is scraped live)
4. Output: `books_data.csv` saved to Colab session

## Key Implementation Details
- `requests.Session()` used for efficient HTTP connection reuse
- 3-retry logic on failed requests
- 0.3s polite delay per page to avoid server overload
- Rating mapped from text (One/Two/Three...) to integer (1/2/3...)

## Sample Output
```
title                                    price_gbp  rating  availability
A Light in the Attic                     51.77      3       In stock
Tipping the Velvet                       53.74      1       In stock
Soumission                               50.10      1       In stock
Sharp Objects                            47.82      4       In stock
Sapiens: A Brief History of Humankind    54.23      5       In stock
```

---
*CodeAlpha Data Analytics Internship · Task 1 of 4*

