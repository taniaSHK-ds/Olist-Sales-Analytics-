# Olist-Sales-Analytics
# Olist E-Commerce Sales & Customer Analytics

End-to-end analysis of a Brazilian e-commerce marketplace using Python and Excel, covering revenue trends, customer segmentation, delivery performance, and a 6-month revenue forecast.

## Business Questions
1. Where does revenue come from (category, state, month) and how is it growing?
2. Who are the most valuable customers (RFM segmentation) and how many come back?
3. Does late delivery hurt customer review scores, and by how much?
4. Which categories and states have the worst delivery performance?
5. What will revenue look like over the next 6 months?

## Dataset
[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle): about 100k orders from 2016 to 2018 across 9 relational tables. Raw files are not stored in this repo.

## Tools
- **Python (pandas, Google Colab):** data cleaning, joins, and feature engineering
- **Excel (web):** PivotTables, slicers, XLOOKUP, SUMIFS, LINEST, FORECAST.ETS, dashboard

## Data Preparation (done)
- Joined 6 relational tables into one analysis table
- Kept delivered orders only and removed orders with no delivery date
- Translated product categories from Portuguese to English
- Kept one review per order
- Engineered features: delivery days, delay days, late flag, order value
- Checked that joins created no duplicate rows, and that item revenue matches payment totals within 0.02%

## Project Structure
- `notebooks/` : Python cleaning and feature engineering
- `data/processed/` : cleaned datasets
- `excel/` : Excel workbook and dashboard
- `images/` : dashboard screenshots

## Status
In progress: Excel analysis and dashboard next.

## Key Insights
Coming soon.

## Recommendations
Coming soon.
