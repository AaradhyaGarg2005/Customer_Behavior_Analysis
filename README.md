# Customer Shopping Behaviour Analysis

An end-to-end analysis of 3,900 retail customer transactions, combining **Python** (data cleaning & feature engineering), **SQL** (business-question queries), and **Power BI** (interactive dashboard) to uncover revenue trends, discount impact, customer segmentation, and product performance.

## Overview

This project takes a raw customer shopping dataset through a full analytics pipeline — from cleaning and feature engineering, through structured SQL analysis, to a live interactive dashboard — to answer real business questions like:

- Who generates more revenue: male or female customers?
- Do subscribed customers actually spend more?
- Which products carry the highest discount rates?
- How does the customer base break down by loyalty segment?
- Which products and age groups drive the most revenue?

## Tech Stack

| Stage | Tool |
|---|---|
| Data cleaning & feature engineering | Python (pandas, Jupyter Notebook) |
| Business analysis | SQL (PostgreSQL) |
| Dashboard & visualization | Power BI |

## Repository Contents

```
├── Customer_Behaviour_Analysis.ipynb   # Data cleaning & feature engineering
├── customer_shopping_behavior.csv      # Cleaned dataset (3,900 rows x 19 columns)
├── customer_behavior.sql               # SQL business-question queries
├── customer_behaviour_Dashboard.pbix   # Power BI dashboard
└── README.md
```

## Data Preparation

- Handled missing `review_rating` values via category-level median imputation
- Standardized column names to snake_case
- Engineered `age_group` (Young Adult / Adult / Middle-aged / Senior) via quantile binning
- Engineered `purchase_frequency_days` from categorical purchase frequency
- Removed redundant duplicate column (`promo_code_used` == `discount_applied`)

## Key Insights

- **Revenue by gender:** Male customers generated $157,890 vs. $75,191 from female customers
- **Discounts:** ~50% of discount users still spent above the average purchase amount ($59.76)
- **Top-rated products:** Gloves, Sandals, Boots, Hats, and Handbags led average review ratings
- **Subscriptions:** Subscribed vs. non-subscribed customers spend almost the same per order ($59.49 vs $59.87) — subscription status doesn't meaningfully drive order value
- **Customer segmentation:** 3,116 Loyal / 701 Returning / 83 New customers
- **Category performance:** Clothing leads revenue ($104K), followed by Accessories ($74K), Footwear ($36K), Outerwear ($19K)
- **Age groups:** Revenue is evenly distributed across age segments (no single group dominates)

## Dashboard

The Power BI dashboard (`customer_behaviour_Dashboard.pbix`) includes:
- KPI cards: Total Customers, Avg. Purchase Amount, Avg. Review Rating
- % of Customers by Subscription Status (donut)
- Revenue & Sales by Category
- Revenue & Sales by Age Group
- Interactive slicers: Subscription Status, Gender, Category, Shipping Type

## How to Use

1. **Data cleaning:** Open `Customer_Behaviour_Analysis.ipynb` in Jupyter to see the cleaning and feature engineering steps.
2. **SQL analysis:** Load `customer_shopping_behavior.csv` into PostgreSQL and run the queries in `customer_behavior.sql`.
3. **Dashboard:** Open `customer_behaviour_Dashboard.pbix` in Power BI Desktop to explore the interactive report.
