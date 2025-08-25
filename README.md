📝 Problem Statement

The management team at Global Superstore, despite seeing steady growth in sales, faced challenges due to uncertain profitability and a lack of deep understanding of their customer base. They needed a comprehensive analytics solution to answer several critical business questions:

What are the key drivers of overall sales and profit?

Which product categories and sub-categories are underperforming or causing financial losses?

Who are our most valuable customers, and how can we segment them for targeted marketing?

What are the expected sales trends for the upcoming year to aid in strategic planning and inventory management?

The goal of this project was to build an end-to-end data pipeline and an interactive dashboard to address these questions and provide actionable, data-driven insights.

🛠️ Tech Stack

Data Storage & Querying: SQLite

Data Analysis & Modeling: Python

Libraries: Pandas (Data Manipulation), Scikit-learn (Clustering & Classification), imbalanced-learn (SMOTE), Prophet (Forecasting), Matplotlib & Seaborn (Visualization)

Business Intelligence & Visualization: Power BI

Dataset: Superstore dataset from kaggle

📂 Project Workflow

1. Data Cleaning & Preparation (Python & Pandas)

The raw dataset was loaded and profiled to identify quality issues.

Key cleaning operations included removing duplicates, standardizing column names, and correcting data types, particularly for date fields.

New features like order_year and shipping_time_days were engineered to support deeper analysis. The final, clean dataset was saved as cleaned_superstore.csv to act as a single source of truth.

2. Database Querying & EDA (SQL)

The cleaned data was imported into an SQLite database to leverage structured querying for analysis.

Initial Exploratory Data Analysis was conducted with SQL to uncover foundational business metrics related to sales, profit, and regional performance.

Advanced SQL techniques were used to perform RFM (Recency, Frequency, Monetary) analysis and Cohort Analysis, preparing the data for machine learning.

3. Machine Learning Modeling (Python & Scikit-learn)

Customer Segmentation: A K-Means Clustering model was applied to the RFM data to group customers into four distinct segments: Champions, Loyal Customers, Needs Attention, and Lost Customers.

Sales Forecasting: A time series model was built using Prophet to forecast monthly sales for the next 12 months, successfully capturing the business's strong yearly seasonality.

Profitability Prediction: A Random Forest Classifier was trained to predict whether an order would be profitable. The significant class imbalance in the data was handled by applying SMOTE (Synthetic Minority Over-sampling Technique) to the training set, which greatly improved the model's ability to identify unprofitable orders.

4. Interactive Visualization (Power BI)

All data sources, including the cleaned data and the customer segmentation results, were connected in Power BI.

A comprehensive, three-page interactive dashboard was designed to present the findings in a compelling narrative, moving from a high-level executive summary to a deep-dive profitability analysis and a final customer intelligence report.

This version gives a much richer picture of the work you did in each step. It's the perfect level of detail for a professional portfolio piece.

💡 Dashboard Solution & Implementation

An interactive, three-page Power BI report was developed to serve as the single source of truth for business performance. Each page was designed to answer a specific set of questions, moving from a high-level overview to a granular, diagnostic analysis.

Page 1: Executive Summary

Purpose: To provide senior leadership with a high-level, at-a-glance overview of the business's health and key performance indicators (KPIs).

Implementation:

KPI Cards: Displaying core metrics like Total Sales, Total Profit, Order Count, and Quantity Sold.

Sales & Profit Trend: A line chart visualizing performance over time, allowing for the identification of growth and seasonality.

Geographic Performance: A map visual showcasing sales distribution across all states.

Performance by Category: Donut and Bar charts breaking down sales by product category and customer segment.

Interactivity: A slicer was included to allow users to filter the entire report by year.

Page 2: Profitability Deep Dive

Purpose: To act as a diagnostic tool for managers to investigate the root causes of low profitability identified in the initial analysis.

Implementation:

Profit by Sub-Category Analysis: A horizontal bar chart with red/green conditional formatting to instantly highlight profitable vs. unprofitable product lines.

Discount Impact Analysis: A scatter plot visualizing the relationship between Sales, Profit, and Discount, clearly showing that higher discounts are correlated with lower profitability.

Root Cause Identification: A bar chart displaying the Average Discount by Sub-Category, directly linking the unprofitable product lines to their high discount rates.

Granular Data Table: A detailed, filterable table of every product, allowing managers to drill down to specific problematic items.

Page 3: Customer Intelligence & Forecasting

Purpose: To present the advanced insights from the Python machine learning models to the marketing and strategy teams.

Implementation:

Customer Segmentation Dashboard: Visuals displaying the size and value (in Sales and Profit) of the four customer segments derived from the K-Means clustering model: Champions, Loyal Customers, Needs Attention, and Lost Customers.

Sales Forecast Chart: A "Line and Clustered Column" chart that overlays the Prophet model's 12-month sales forecast onto the historical actual sales data, providing a clear view of expected future trends.





