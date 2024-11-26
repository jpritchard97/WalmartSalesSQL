# Walmart Sales Data Analysis

## Overview

This project delves into an extensive analysis of sales data from various Walmart branches to uncover insights into customer behavior, product performance, and sales trends. The goal is to identify key factors influencing sales, allowing for recommendations on improving business strategies. The dataset used is from the Kaggle Walmart Sales Forecasting Competition, which provides historical data on sales across 45 Walmart stores, including different departments and holiday markdowns.

## Project Objectives

The main goal of this analysis is to examine Walmart's sales data in order to better understand sales performance at both the product and branch level. Specifically, we seek to explore:

- Top-performing products and branches
- Trends in customer purchasing behaviors
- Potential areas to optimize sales strategies

## Dataset Description

The dataset, sourced from the Kaggle Walmart Sales Forecasting Competition, includes sales transactions from three Walmart branches located in Mandalay, Yangon, and Naypyitaw. The dataset comprises 17 columns and 1000 rows with the following information:

| Column                 | Description                                           | Data Type       |
|------------------------|-------------------------------------------------------|-----------------|
| invoice_id             | Unique identifier for each sale transaction          | VARCHAR(30)     |
| branch                 | Branch location where the sale occurred               | VARCHAR(5)      |
| city                   | City where the branch is located                      | VARCHAR(30)     |
| customer_type          | Type of customer making the purchase                  | VARCHAR(30)     |
| gender                 | Gender of the purchasing customer                     | VARCHAR(10)     |
| product_line           | Product category of the sold item                     | VARCHAR(100)    |
| unit_price             | Price per unit of the product sold                    | DECIMAL(10, 2)  |
| quantity               | Number of units sold                                  | INT             |
| VAT                    | Value-added tax on the purchase                       | FLOAT(6, 4)     |
| total                  | Total cost including VAT and product price            | DECIMAL(10, 2)  |
| date                   | Date of the sale                                      | DATE            |
| time                   | Time the sale took place                              | TIMESTAMP       |
| payment_method         | Method used for payment                               | VARCHAR(20)     |
| cogs                   | Cost of goods sold                                    | DECIMAL(10, 2)  |
| gross_margin_percentage| Gross margin percentage (profit margin)               | FLOAT(11, 9)    |
| gross_income           | Gross income (revenue minus cost)                     | DECIMAL(10, 2)  |
| rating                 | Customer rating for the product                       | FLOAT(2, 1)     |

## Analysis Focus Areas

### 1. Product Performance Analysis

This section aims to identify which product lines and specific products are the top performers. By analyzing sales patterns, we can determine areas for improvement and future investment.

### 2. Sales Trend Analysis

Understanding sales trends over time will help evaluate the effectiveness of sales strategies and inform decisions about seasonal or promotional efforts. The goal is to detect which periods and product lines generate the highest revenue and profitability.

### 3. Customer Behavior Analysis

In-depth customer segmentation is explored to determine purchasing patterns, product preferences, and which customer groups generate the most revenue.

## Methodology

### Data Wrangling & Cleaning

The first step involves ensuring the dataset is clean, with no missing or NULL values. This is done by inspecting the data and applying appropriate methods to fill or remove any gaps.

- A database is set up, and the data is loaded into structured tables.
- NULL values are handled, and fields are set to NOT NULL where necessary.

### Feature Engineering

Several new features are derived from existing data to enhance the analysis:

- **Time of Day**: A new column categorizes the sales time into Morning, Afternoon, and Evening, which helps in understanding peak shopping hours.
- **Day of the Week**: This feature extracts the day of the week (Monday, Tuesday, etc.) to identify trends related to weekday sales.
- **Month of the Year**: By adding the month, we can observe which months show the highest sales activity.

### Exploratory Data Analysis (EDA)

Using statistical analysis and visualization techniques, we examine the relationships between various factors, such as sales, customer types, product categories, and city-based trends.

## Business Questions to Answer

**General Questions:**
- How many unique cities are in the dataset?
- Which city is associated with each branch?

**Product-Specific Questions:**
- What are the most common payment methods?
- What is the best-performing product line based on sales?
- Which month generates the most revenue?
- Which product line generates the most VAT?

**Customer Insights:**
- How many unique customer types are present in the data?
- What is the gender distribution for each branch?
- What is the average customer rating per product line?

## Revenue and Profit Calculations

The key metrics to calculate revenue and profit are as follows:

- **Cost of Goods Sold (COGS)**: `COGS = unit_price * quantity`
- **VAT**: `VAT = 5% of COGS`
- **Total Sales (Gross Sales)**: `Total = VAT + COGS`
- **Gross Profit (Gross Income)**: `Gross Income = Total Sales - COGS`
- **Gross Margin**: `Gross Margin = Gross Income / Total Revenue`

Example Calculation:

Given the following data:
- **Unit Price**: 45.79
- **Quantity**: 7

The **COGS** is calculated as:

\[
COGS = 45.79 \times 7 = 320.53
\]

Then, the **VAT** is:

\[
VAT = 0.05 \times 320.53 = 16.03
\]

The **Total Sales** becomes:

\[
Total = 320.53 + 16.03 = 336.56
\]

Finally, the **Gross Margin** is:

\[
Gross Margin = \frac{16.03}{336.56} \approx 4.76\%
\]

## Conclusion

By exploring the dataset from various angles, this project aims to provide actionable insights into how Walmart can optimize its sales strategies across different regions and product categories. Future work will involve building predictive models to forecast sales based on historical data.
