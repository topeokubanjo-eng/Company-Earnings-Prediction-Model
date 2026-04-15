# 📚 Book Sales Data Analysis

## Overview
This project is an exploratory data analysis (EDA) of a book sales dataset covering **1,070 books** across multiple genres, publishers, and author tiers. The goal is to uncover patterns in sales performance, pricing strategy, ratings, and publisher behaviour — and communicate those findings through clear, multi-layered visualizations.

The analysis emphasizes **visual storytelling** using stacked area charts, violin plots, correlation heatmaps, and multi-variable scatter plots to go beyond basic summary statistics.

---

## Project Objectives
- Analyze how book sales have trended across publishing decades and genres
- Examine the relationship between pricing, ratings, and units sold
- Profile top-performing authors and publishers
- Identify correlations between key numeric variables to surface hidden drivers of revenue

---

## Dataset
The dataset (`Books_Data_Clean.csv`) contains 15 features per book, including:

| Feature | Description |
|---|---|
| `Book Name` | Title of the book |
| `Author` | Author name |
| `genre` | Genre category (genre fiction, fiction, nonfiction, children) |
| `Publishing Year` | Year the book was published |
| `sale price` | Retail price in USD |
| `units sold` | Number of units sold |
| `gross sales` | Total gross revenue |
| `publisher revenue` | Revenue retained by the publisher |
| `Book_average_rating` | Average reader rating |
| `Book_ratings_count` | Total number of ratings received |
| `Author_Rating` | Author experience tier (Novice → Famous) |
| `Publisher` | Publishing house |

---

## Tools & Libraries
![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-lightgrey?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-teal)

---
## Interactive PowerBI Dashboard
![PowerBi Screenshot](https://github.com/user-attachments/assets/a2c35abd-37fb-42d0-92df-46ff6e448887)

- Sales by Author
  - Compares gross sales across authors
  - Helps identify top-performing authors

- Language Distribution of Sales
  - Shows contribution of sales by language code
  - Useful for understanding market/language concentration

- Units Sold per Sale Price
  - Visualizes relationship between price points and units sold
  - Helps identify pricing patterns

- Units Sold Over Time
  - Tracks units sold by publishing year
  - Highlights long-term trends and spikes in recent years

### Tools Used

- Python (data cleaning / analysis)
- Excel (cleaned dataset)
- Power BI (interactive dashboard)

### How to Open the Dashboard

- Download the `.pbix` file from this repository
- Open it in Power BI Desktop

---
## Visualizations & Key Insights

### Figure 1 — Publishing Trends & Genre Landscape
<img width="2283" height="1405" alt="image" src="https://github.com/user-attachments/assets/bb0b0bf6-2cfc-4d3b-88c0-7ebcf43c28aa" />


**Insights:**
- **Genre fiction dominates** — it accounts for **76.8%** of all titles in the dataset, with nonfiction a distant second at 16.2%
- **Sales volume surged in the 2000s**, peaking around 2010–2013 before declining, likely reflecting a boom in digital self-publishing followed by market saturation
- The **KDE density plot** reveals that genre fiction and nonfiction titles are concentrated heavily in the post-2000 era, while children's books have a flatter, broader publishing history
- Despite being the smallest genre by volume, **children's books average the highest units sold per title (~19,875)**, nearly double nonfiction and genre fiction (~9,700) — indicating a highly concentrated, high-performing niche

---

### Figure 2 — Pricing, Ratings & Revenue
<img width="2250" height="1535" alt="image" src="https://github.com/user-attachments/assets/fc35c5cc-6edb-42b4-9bd3-c6031502c8bd" />


**Insights:**
- **Price and units sold have a weak negative relationship** — the scatter plot and trend line show that most high-volume books are priced between $1–$5, reinforcing that lower price points drive higher volume sales
- **Famous authors command both higher ratings and more consistent quality** — the violin plot shows that books by Famous-tier authors cluster tightly around 4.25–4.5 stars, while Novice authors have far wider variance and a lower median (~3.4)
- The **3-variable scatter** (rating × ratings count, coloured by units sold) shows that the highest-selling books aren't always the highest rated — popularity (ratings count) is a stronger signal of sales volume than average rating alone
- **Fiction generates the highest average gross sales (~$2,200)** despite being only 5.5% of titles, suggesting individual fiction titles perform exceptionally well — a quality-over-quantity dynamic

---

### Figure 3 — Authors, Publishers & Correlations
<img width="2365" height="1588" alt="image" src="https://github.com/user-attachments/assets/dd913338-419f-4b06-9134-2421bcd09a86" />

**Insights:**
- **Harper Lee leads all authors in gross sales ($47,795)**, followed closely by Stephen King ($43,323) and David Sedaris ($42,323) — a mix of literary fiction and popular nonfiction at the top
- **Amazon Digital Services dominates by volume** but is heavily concentrated in genre fiction, while traditional publishers like Random House and HarperCollins maintain a more balanced genre mix across their catalogues
- The **units sold boxplot by author tier** reveals a surprising pattern: Excellent-rated authors have the widest spread and highest ceiling — suggesting this tier contains breakout hits — while Famous authors have tight, moderate distributions, possibly due to smaller catalogue sizes in this dataset
- The **correlation heatmap** highlights that `gross sales` and `publisher revenue` are very strongly correlated (r = 0.92), confirming publishers' revenue is near-linearly tied to gross performance. Notably, `units sold` shows a **negative correlation with ratings count (r = -0.25)**, suggesting that books with massive rating counts are not necessarily the top sellers by volume — an interesting tension between visibility and sales conversion

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/topeokubanjo-eng/book-sales-data-analysis.git
cd book-sales-data-analysis

# Install dependencies
pip install pandas matplotlib seaborn numpy

# Run the notebook
jupyter notebook Book_Sales_Analysis_Enhanced.ipynb
```

Make sure `Books_Data_Clean.csv` is in the same directory as the notebook.

---

## File Structure
```
📁 Book Sales Data Analysis
├── 📓 Book_Sales_Analysis_Enhanced.ipynb   # Main analysis notebook
├── 📄 Books_Data_Clean.csv                 # Cleaned dataset
├── 📁 images/
│   ├── fig1_trends_genre.png               # Publishing Trends & Genre Landscape
│   ├── fig2_pricing_ratings.png            # Pricing, Ratings & Revenue
│   └── fig3_authors_publishers.png         # Authors, Publishers & Correlations
└── 📄 README.md
```

---

## Key Takeaways

> 🔑 **Children's books punch far above their weight** — fewest titles, highest average sales per book  
> 🔑 **Price elasticity is real** — the sweet spot for volume is under $5  
> 🔑 **Author prestige correlates with rating consistency**, not necessarily peak sales  
> 🔑 **Gross sales and publisher revenue move almost in lockstep** (r = 0.92)  
> 🔑 **Post-2000 publishing dominates the dataset**, but peak volume came around 2010–2013
