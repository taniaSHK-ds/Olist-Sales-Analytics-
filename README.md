# Olist E-Commerce Sales & Customer Analytics

End-to-end analysis of a Brazilian e-commerce marketplace using Python and Excel: revenue trends, regional concentration, customer retention, delivery performance, and a 6-month revenue forecast.

## Business Questions
1. Where does revenue come from (state, category, month) and how is it growing?
2. Who are the most valuable customers, and how many come back?
3. Does late delivery hurt customer review scores, and by how much?
4. Which categories and states have the worst delivery performance?
5. What will revenue look like over the next 6 months?

## Dataset
[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle): about 100k orders from 2016 to 2018 across 9 relational tables. Raw files are not stored in this repo.

## Tools
- **Python (pandas, Google Colab):** cleaning, joins, feature engineering
- **Excel for the web:** Tables, PivotTables, formulas, dashboard

## Data Preparation
| Step | Result |
|---|---|
| Raw orders | 99,441 |
| Non-delivered orders removed (shipped, canceled, unavailable, etc.) | 2,963 |
| Delivered orders with no delivery date removed | 8 |
| Orders before 2017 removed (only 267 orders, platform still launching) | 267 |
| **Final orders analysed** | **96,203** |
| Duplicate order IDs | 0 |
| Orders with no review score (left empty, not imputed) | 643 |
| Item revenue vs payment totals (reconciliation gap) | 0.02% |

Other steps:
- Joined items, orders, customers, products, sellers, and reviews into one item-level table, then checked that the joins created no extra rows
- Translated product categories from Portuguese to English; categories missing in the source are labelled `unknown`
- Kept one review per order (the latest)
- Skipped the geolocation table (about 261k duplicate rows; state-level location is enough for this analysis)
- Engineered features: delivery days, delay days vs the promised date, late flag, order value

## Key Metrics (Jan 2017 to Aug 2018)
| Metric | Value |
|---|---|
| Orders | 96,203 |
| Unique customers | 93,096 |
| Item revenue | 13.18M BRL |
| Freight | 2.19M BRL |
| Average order value (incl. freight) | 159.78 BRL |
| Average review score | 4.16 / 5 |
| Late delivery rate | 8.13% |
| Average delivery time | 12.1 days |

## Early Insights
1. **Growth levelled off in 2018.** Monthly item revenue rose from about 112k in January 2017 to a peak of about 988k in **November 2017** (Black Friday), then stayed between about 826k and 978k a month through August 2018.
2. **Revenue is concentrated in three states.** São Paulo, Rio de Janeiro, and Minas Gerais generate about **63%** of item revenue (SP alone 38%). The top 5 states generate about 74%.
3. **Shipping adds about 17% to item revenue.** Freight totals 2.19M on 13.18M of items.
4. **Customers rarely return.** There are 96,203 orders but 93,096 unique customers, about 1.03 orders per customer. The exact repeat rate comes with the RFM analysis.
5. **Most deliveries are on time.** About 92% of orders arrive by the promised date.

## Coming Soon
- Revenue by product category
- Repeat purchase rate and RFM customer segments
- Impact of late delivery on review scores
- Worst-performing categories and states for delivery
- 6-month revenue forecast
- Excel dashboard
- Recommendations

## Repository Structure
- `notebooks/`: Python cleaning and feature engineering
- `data/processed/`: cleaned datasets
- `excel/`: Excel workbook and dashboard
- `images/`: dashboard screenshots

## Status
In progress. Completed: data preparation and revenue analysis. Next: customer retention (RFM) and delivery impact.
