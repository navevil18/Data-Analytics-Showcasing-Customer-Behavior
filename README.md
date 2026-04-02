# 🛒 Customer Shopping Behavior — End-to-End Data Analytics Project

> A complete data analytics pipeline covering Python EDA, PostgreSQL querying, Power BI dashboarding, and business reporting — built on 3,900 real customer transactions.

---

## 📌 Project Overview

This project performs a full-cycle analysis of customer shopping behavior to uncover patterns in revenue, product preferences, discount usage, and customer loyalty. The analysis moves through every stage of a real-world data pipeline — from raw data ingestion to an executive-ready dashboard and presentation.

**Key questions answered:**
- Which customer segments generate the most revenue?
- Do subscribers spend more than non-subscribers?
- Which products rely heavily on discounts?
- How does loyalty segment distribute across the customer base?

---

## 📂 Dataset

| Attribute        | Detail                                  |
|------------------|-----------------------------------------|
| **Source**       | Synthetic retail transaction dataset    |
| **Rows**         | 3,900                                   |
| **Columns**      | 18                                      |
| **Missing Data** | 37 nulls in `review_rating` (imputed)  |

**Feature groups:**

| Group                  | Columns                                                                 |
|------------------------|-------------------------------------------------------------------------|
| Customer Demographics  | Age, Gender, Location, Subscription Status                              |
| Purchase Details       | Item Purchased, Category, Amount (USD), Season, Size, Color             |
| Shopping Behaviour     | Discount Applied, Promo Code Used, Previous Purchases, Frequency, Rating, Shipping Type |

---

## 🛠️ Tools & Technologies

| Tool            | Purpose                                      |
|-----------------|----------------------------------------------|
| **Python**      | Data loading, EDA, cleaning, feature engineering |
| **pandas**      | DataFrame manipulation and analysis          |
| **PostgreSQL**  | SQL querying and business logic              |
| **Power BI**    | Interactive dashboard                        |
| **Gamma**       | Presentation slide deck                      |

---

## 🔄 Project Steps

### Step 1 — Python: Data Loading & EDA
- Loaded the dataset using `pandas`
- Explored structure with `df.info()` and `df.describe()`
- Identified 37 missing values in the `review_rating` column

### Step 2 — Python: Data Cleaning
- Imputed missing `review_rating` values with **per-category median**
- Renamed all columns to `snake_case` for consistency
- Dropped the redundant `promo_code_used` column (duplicate of `discount_applied`)
- Verified no remaining data quality issues

### Step 3 — Python: Feature Engineering
- Created `age_group` bins: `Young Adult`, `Adult`, `Middle-aged`, `Senior`
- Derived `purchase_frequency_days` column

### Step 4 — PostgreSQL: SQL Analysis
- Loaded the cleaned DataFrame into PostgreSQL
- Wrote **10 business queries** covering revenue, segmentation, product ranking, and discount analysis
- (See [`Customer_Behaviour.sql`](Customer_Behaviour.sql) for all queries)

### Step 5 — Power BI: Dashboard
- Built an interactive dashboard with KPI cards, category breakdowns, and revenue charts
- Added slicers for Subscription Status, Gender, Category, and Shipping Type

### Step 6 — Reporting & Presentation
- Compiled findings into a structured PDF report
- Built an executive-facing slide deck using **Gamma**

---

## 📊 Dashboard Preview

The Power BI dashboard includes:

- **KPI Cards** — 3.9K Customers | $59.76 Avg Spend | 3.75 Avg Rating
- **Subscription Split** — 27% Subscribed vs 73% Not Subscribed
- **Revenue by Category & Age Group**
- **Slicers** — Filter by Subscription, Gender, Category, Shipping Type

> 📁 File: `customer_Shopping_Behavior.pbix`

---

## 📈 Key Results

| Question                               | Finding                                          |
|----------------------------------------|--------------------------------------------------|
| Revenue by Gender                      | Male: $157,890 | Female: $75,191                 |
| High-spend discount users              | 839 customers used discounts & spent above avg   |
| Top-rated product                      | Gloves (3.86 avg rating)                         |
| Shipping vs Spend                      | Express: $60.48 avg | Standard: $58.46 avg       |
| Subscriber avg spend vs non-subscriber | $59.49 (Yes) vs $59.87 (No) — minimal difference |
| Most discount-dependent product        | Hat (50% discount rate)                          |
| Largest customer segment               | Loyal: 3,116 | Returning: 701 | New: 83           |
| Highest revenue age group             | Young Adults: $62,143                            |

---

## 💡 Business Recommendations

1. **Boost Subscriptions** — Only 27% are subscribed; promote exclusive perks to drive enrollment
2. **Loyalty Programs** — Reward repeat buyers to retain the large loyal segment
3. **Discount Policy Review** — Hat and Sneakers show ~50% discount rates; review margin impact
4. **Product Marketing** — Feature top-rated items (Gloves, Sandals, Boots) in campaigns
5. **Targeted Marketing** — Prioritize Young Adults and Express shipping users for highest ROI

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/navevil18/Data-Analytics-Showcasing-Customer-Behavior.git
cd Data-Analytics-Showcasing-Customer-Behavior
```

### 2. Run the Python Notebook
```bash
# Install dependencies
pip install pandas sqlalchemy psycopg2

# Open the notebook
jupyter notebook Customer_Cleaned_Data.ipynb
```

### 3. Set Up PostgreSQL
```sql
CREATE DATABASE customer_behavior;
-- Then run the queries in Customer_Behaviour.sql
```

### 4. Open the Power BI Dashboard
- Open `customer_Shopping_Behavior.pbix` in **Power BI Desktop**
- Refresh data source if needed

---

## 📁 Repository Structure

```
📦 Customer-Shopping-Behavior
 ┣ 📄 customer_shopping_behavior.csv          ← Raw dataset
 ┣ 📓 Customer_Cleaned_Data.ipynb             ← Python EDA & cleaning
 ┣ 🗄️  Customer_Behaviour.sql                 ← SQL queries (PostgreSQL)
 ┣ 📊 customer_Shopping_Behavior.pbix         ← Power BI dashboard
 ┣ 📝 Customer_Shopping_Behavior_Analysis.pdf ← Full analysis report
 ┗ 📄 README.md                               ← You are here
```

---

## 👤 Author

**Naveen** — [@navevil18](https://github.com/navevil18)

*Data Analytics | Python | SQL | Power BI*

---

> ⭐ If you found this project useful, consider starring the repository!
