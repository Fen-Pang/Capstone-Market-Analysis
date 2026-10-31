**Prepared By: Pang Fuh Yun (Fen)**<br>
**Datasets Used: customer.csv and purchase.csv**

# [Capstone Project] Market Analysis – Retail Customer Purchase Analytics

## Problem Statement
How can customer demographics, buying patterns and product performance be used to identify high-value customers and improve retail sales?

## 5 Research Objectives
1. Analyse sales and purchasing trends to understand how sales change over time.
2. Identify best-selling products and their contribution to overall sales.
3. Analyse customer demographics and spending behaviour to understand different customer groups.
4. Identify high-value customers based on total spending and purchase frequency.
5. Compare sales performance across different customer groups and countries to identify opportunities for sales growth.

## 📊 Dataset Overview

This project uses customer and purchase datasets to analyse retail sales performance, product sales and customer purchasing behaviour. The aim is to identify high-value customers and opportunities to improve retail sales.

- Files Used: customer.csv and purchase.csv
- Time Horizon: August 2019 – January 2023
- Analysis Focus: Retail Customer Purchases
- Main Data: Customer Demographics, Purchase Transactions, Product Sales, Revenue and Customer Spending

Google Colab Notebook: https://colab.research.google.com/drive/12rAB9Mje8lND-tTlanhnksDgYOUWpMtP
   
## 📁 Data Dictionary
The project uses two datasets containing 18 columns in total.

### Customer Dataset (customer.csv)
Contains 1,001 customers and 7 features.

| Column Name | Data Type | Description | Example Value |
| :--- | :--- | :--- | :--- |
| **customer_id** | String | A unique ID for each customer. | `CS00001` |
| **first_name** | String | The customer's first name. | `Isadora` |
| **last_name** | String | The customer's last name. | `Porto` |
| **gender** | String | The customer's gender. | `Female` |
| **age** | Integer | The customer's age. | `19` |
| **country** | String | The customer's country. | `Brazil` |
| **income** | Integer | The customer's income. | `117196` |


### Purchase Dataset (purchase.csv)
Contains 50,000 purchases and 11 features.

| Column Name | Data Type | Description | Example Value |
| :--- | :--- | :--- | :--- |
| **order_id** | String | A unique ID for each order. | `ODSHP00001` |
| **customer_id** | String | The ID of the customer who made the purchase. | `CS00001` |
| **product_name** | String | The name of the product purchased. | `Furniture` |
| **description** | String | Description of the product. | `Transform your space with this stylish and functional furniture.` |
| **price** | Float | The price of the product. | `645.52` |
| **discount** | Float | Discount applied to the purchase. | `0.37` (37%) |
| **tax** | Float | Tax applied to the purchase. | `0.02` (2%) |
| **order_date** | Date | The date the order was placed. | `26/5/2020` |
| **quantity** | Integer | The number of units purchased. | `9` |
| **shipping_cost** | Float | The shipping cost of the order. | `8.91` |
| **shipping_date** | Date | The date the order was shipped. | `29/5/2020` |


## 🔍 Data Quality & Cleaning Notes

## 🔍 Data Quality & Cleaning Notes

Data checking and preparation were completed using Python in Google Colab.

- Customer dataset: 1,001 rows and 7 columns
- Purchase dataset: 50,000 rows and 11 columns
- No missing values or duplicate rows were found
- Checked customer IDs in the customer dataset and order IDs in the purchase dataset. Both were unique.
- Checked gender, country and product names. No obvious inconsistencies were found.
- Converted order_date and shipping_date to datetime format.
- Calculated sales revenue after discounts.
- Used a box plot to check purchase-price outliers. Some unusually high prices were identified as potential outliers, but no records were removed solely because of their high values.
- All 50,000 purchases were made by 1,000 customers. One customer had no recorded purchases.
- All 1,000 purchasing customers made exactly 50 purchases each.

Based on these checks, no further data cleaning was needed. The prepared datasets were saved as customer_cleaned.csv and purchase_cleaned.csv for Power BI.

## 💡 Key Findings from Python Analysis
Based on the analysis in Google Colab:
1. Sales Trends: Total actual sales revenue was approximately $263.69 million. Monthly sales were mostly around $6 to $7 million.
2. Product Sales: Curtains generated the highest revenue ($18.62 million), while Sports Shoes had the highest quantity sold (9,642 units).
3. Customer Demographics: Male customers generated slightly higher sales than female customers. Customers aged 51 had the highest average spending per purchase.
4. High-Value Customers: Customer CS00609 recorded the highest total spending ($446,568.14). All 1,000 purchasing customers made 50 purchases each, so total spending was used to distinguish high-value customers.
5. Sales by Country: Highest is Colombia ($74.37 million) and lowest is Brazil ($60.79 million).

## 📊 Power BI Dashboard – Descriptive Analytics

### Dashboard 1: Sales & Product Performance
This dashboard supports Research Objectives 1, 2 and 5. It visualises monthly sales trends, product performance by revenue and quantity sold, and sales performance across countries.

The dashboard shows best-selling products, sales patterns and areas where sales could improve.
<img width="962" height="539" alt="image" src="https://github.com/user-attachments/assets/1cc521a4-bca0-4a72-b6c2-ec8af7f614ab" />

### Dashboard 2: Customer Analysis
This dashboard supports Research Objectives 3 and 4. It compares customer spending by gender and age, and identifies the top 10 customers based on total spending.

These visualisations help identify high-spending customers and customer groups that could be useful for future marketing activities.
<img width="880" height="512" alt="image" src="https://github.com/user-attachments/assets/ffd7442b-cdc5-444a-bd02-57731ca0458f" />


## 📈 Predictive Analytics – Multiple Linear Regression

I used Multiple Linear Regression to predict sales revenue per individual purchase (Y) using 5 variables (X) - Month Number, Customer Age, Gender, Country and Product Name.

I chose this approach because I wanted to understand how customer information and product choices relate to purchase values, which could help the company plan better product strategies.

I used an 80/20 training and testing split, and the model achieved an R² of 35.55%. I also tried replacing Month Number with Customer Income, but the R² was slightly lower at 35.49%. Therefore, I kept my original model.

## 🛠️ Tools Used
1. Python (Google Colab) – Data cleaning, combining datasets, data analysis and charts.
2. Power BI – Creating interactive dashboards to analyse sales, customers and products.
3. GitHub – Storing project files, documentation and tracking project progress.
