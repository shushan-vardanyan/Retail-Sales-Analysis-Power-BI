# Retail Sales Analysis — Power BI

An end-to-end Power BI project covering data cleaning, star schema modeling, DAX measures, and interactive report design.

## Project Overview

This project analyzes a synthetic retail sales dataset containing approximately **500,000 rows**, covering **2023–2025**. Sales amounts are expressed in **Armenian dram (AMD)**.

The goal was to transform a raw, flat dataset into a structured data model and build an interactive dashboard for exploring revenue, profitability, stores, products, and customers.

**The dataset is synthetic and was generated for learning and portfolio purposes. It does not represent a real business.**

## Tools Used

- **Power Query** — data cleaning and transformation
- **Power BI Desktop** — data modeling and report development
- **DAX** — business measures and calculations

## Data Preparation

I cleaned and transformed the raw dataset in Power Query, including:

- Removing duplicate records.
- Standardizing text values and category labels.
- Handling missing and invalid values.
- Converting mixed date formats into a consistent Date type.
- Replacing invalid date values with null.
- Assigning appropriate column data types.
- Preparing discount values for revenue calculations.

## Data Modeling

I separated the flat dataset into a central fact table and dimension tables to create a **star schema**.

| Table | Purpose |
|---|---|
| Retail_Sales | Order lines, transaction details, quantities, prices, costs, and discounts |
| Customers | Customer attributes and segments |
| Products | Product names, categories, subcategories, and brands |
| Stores | Store names and locations |
| DimDate | Calendar attributes for date filtering and time-based analysis |

The model uses one-to-many relationships with single-direction filtering from dimensions to the fact table.

The date table connects to order date through an active relationship and ship date through an inactive relationship.

## DAX Measures

I created the following measures:

- Total Revenue
- Total Cost
- Gross Profit
- Gross Margin %
- Completed Orders
- Average Order Value
- Units Sold
- Active Customers

Revenue is calculated after discounts for completed sales. Returned and cancelled transactions are excluded from revenue and profit calculations.

Orders are counted using distinct order IDs to avoid counting multi-line orders more than once. Shipping fees are excluded from the revenue and gross profit definitions used in this report.

## Dashboard Features

The Sales Overview page includes:

- KPI cards for key sales and profitability metrics.
- A monthly revenue trend.
- Gross profit by product category.
- Revenue by sales channel.
- A store performance matrix showing the top six stores by revenue.
- Slicers for year, category, store, and channel.
- Bookmarks for navigating saved report views.
- Clear all Slicers button

The visuals respond to filter selections, allowing users to explore different periods and business segments.

## Business Questions

The report helps answer:

- How much revenue and gross profit do completed sales generate?
- How does revenue change over time?
- Which product categories generate the most profit?
- Which stores generate the highest revenue?
- Which sales channels contribute the most revenue?
- What is the average order value?
- How many customers make completed purchases?

## Repository Contents

| File | Description |
|---|---|
| Retail_Sales_Raw_500000.csv | Original dataset with intentional data-quality issues |
| Retail_Sales_Dashboard.pbix | Power BI model, transformations, measures, and report |
| README.md | Project documentation |

## How to Use

1. Download the CSV and PBIX files.
2. Open the PBIX file in Power BI Desktop.
3. If refreshing the data, update the CSV source path in Power Query to match its location on your computer.
4. Refresh the report and explore it using the slicers and bookmarks.

## Skills Demonstrated

Data cleaning · Power Query · Star schema modeling · DAX · Data visualization · Interactive reporting · Business analysis
