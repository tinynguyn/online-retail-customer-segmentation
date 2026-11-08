# Online Retail Sales Analysis & Customer Segmentation

A Python data analysis project exploring online retail transactions from 2009 to 2011. The goal is to understand sales trends and group customers based on their purchasing behavior using **RFM analysis**.

## Project Overview

This project focuses on three questions:

- How does sales revenue change over time?
- How can customers be grouped based on their purchase history?
- Which customer segments contribute the most revenue?

## Tools

- **Python**
- **Pandas** for data cleaning and analysis
- **Matplotlib & Seaborn** for visualizations
- **Jupyter Notebook**

## Dataset

The project uses the **Online Retail II** dataset, containing transaction records from two Excel sheets (`Year 2009-2010` and `Year 2010-2011`).

The analysis combines both sheets into one dataset and works with transaction information such as invoice dates, quantities, prices, and customer IDs.

Place `online_retail_II.xlsx` in the `data/` folder

## Analysis Steps

### 1. Data exploration and cleaning

- Check column types, missing values, duplicate rows, and unusual quantities or prices.
- Remove duplicate rows and records without a customer ID.
- Keep transactions with positive quantities and prices for this sales and customer analysis.

### 2. Sales analysis

- Calculate revenue as `Quantity × Price`.
- Aggregate revenue by month.
- Visualize monthly revenue trends.

### 3. RFM analysis

Calculate three metrics for each customer:

| Metric | Meaning |
| --- | --- |
| **Recency (R)** | Days since the customer's latest purchase |
| **Frequency (F)** | Number of unique invoices |
| **Monetary (M)** | Total revenue from the customer's purchases |

Each metric is scored from 1 to 5. Customers are then assigned to six groups using their Recency and Frequency scores: **Champions, Loyal Customers, At Risk, Inactive, Recent Low Frequency, and Other**.

### 4. Segment comparison

- Visualize customer counts across Recency and Frequency scores.
- Compare customer segments by size and revenue contribution.
- Compare **customer share** and **revenue share** in a bar chart.

## Key Findings

- Monthly sales show a seasonal increase toward **September–November** in both years.
- **Champions** represent approximately **9.6% of customers** but generate around **48% of analyzed revenue**.
- **Loyal Customers** contribute approximately **30.9% of revenue**.
- Together, these two groups contribute roughly **79% of revenue**, suggesting that a relatively small group of customers accounts for much of the positive-sales revenue.

These findings can help a business identify valuable customer groups and explore different retention or engagement strategies. They do not establish which strategy would be effective without further testing.

## Project Structure

```text
online-retail-customer-segmentation/
├── notebook/
│   └── analysis.ipynb
├── data/
│   └── online_retail_II.xlsx   
├── chart/                       
├── .gitignore
└── README.md
```


## Limitations

- The analysis excludes returns, non-positive transactions, and records without customer IDs. Therefore, the revenue shown is **positive sales revenue**, not net revenue after returns.
- RFM segments are based on simple rules and are not predictions of future customer behavior.
- The scoring uses ranked values to create five groups; customers with the same original metric may receive different scores when ties are broken.
- The first and last months of the dataset may be incomplete, so monthly comparisons require care.

## What I Learned

Through this project, I practiced checking data quality, cleaning transaction records, creating business metrics, and using visualizations to communicate customer and sales insights.
