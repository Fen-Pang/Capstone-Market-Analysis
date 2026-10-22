**Prepared By: Pang Fuh Yun (Fen)**<br>
**Datasets Used: Customer.csv and Purchase.csv**

# [Capstone Project] Market Analysis – Retail Customer Purchase Analytics
<add image>

## Problem Statement
How can customer demographics, buying patterns and product performance be used to identify high-value customers and enhance retail sales?

## 5 Research Objectives
1. Analyse sales and purchasing trends to identify opportunities to increase revenue.
2. Identify best-selling products and their contribution to overall sales to improve product strategies.
3. Analyse customer demographics and spending behaviour to improve customer targeting.
4. Identify high-value customers based on total spending and purchase frequency to support customer retention.
5. Compare sales performance across different customer groups and countries to identify opportunities for sales growth.

<h1>Retail Customer and Purchase Datasets📊</h1>

This repository contains two datasets, customer.csv and purchase.csv, covering customer demographics, purchasing behaviour and retail product sales transactions. It include customer information such as age, gender, income and country, alongside purchase details such as product names, prices, quantities, order dates and shipping costs.

These datasets can be used for exploratory data analysis (EDA), sales performance analysis, customer segmentation and product performance analysis to better understand customer purchasing behaviour and identify sales opportunities.

<img width="1317" height="742" alt="image" src="https://github.com/user-attachments/assets/fd2d0b2f-b7d0-4953-8c8b-868132c2485a" />

## 📋 Dataset Overview

* **File Name:** `customer.csv and purchase.csv`
* **Time Horizon:** Aug 2019 - Jan 2023
* **Target Category:** Retail Customer Purchases
* **Key Entities:** Customer Demographics, Purchase Transactions, Product Sales, Revenue and Customer Spending

  Link to Google Colab Notebook: https://colab.research.google.com/drive/12rAB9Mje8lND-tTlanhnksDgYOUWpMtP#scrollTo=8lWK9xViT9wn&uniqifier=1
   
## 📁 Data Dictionary
The project uses two datasets with a total of 18 features.

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
| **order_id** | String | A unique ID for each order. | `Order ID` |
| **customer_id** | String | The ID of the customer who made the purchase. | `CS00001` |
| **product_name** | String | The name of the product purchased. | `Furniture` |
| **description** | String | Description of the product. | `Product description` |
| **price** | Float | The price of the product. | `20.02` |
| **discount** | Float | Discount applied to the purchase. | `0.25` (25%) |
| **tax** | Float | Tax applied to the purchase. | `0.05` (5%) |
| **order_date** | Date | The date the order was placed. | `DD/MM/YYYY` |
| **quantity** | Integer | The number of units purchased. | `5` |
| **shipping_cost** | Float | The shipping cost of the order. | `27.50` |
| **shipping_date** | Date | The date the order was shipped. | `DD/MM/YYYY` |

## 🔍 Data Quality & Cleaning Notes

Data checking and preparation were completed using Python in Google Colab.
- Customer dataset: 1,001 rows and 7 columns
- Purchase dataset: 50,000 rows and 11 columns
- No missing values or duplicate rows were found
- Customer IDs and order IDs were checked and found to be unique
- Checked gender, country and product names. No obvious inconsistencies were found
- Converted order_date and shipping_date to datetime format
- Calculated sales revenue after discounts

Based on these checks, no further data cleaning was needed. The prepared datasets were saved as customer_cleaned.csv and purchase_cleaned.csv for Power BI.

## 🛠️ Usage Example (Python & Pandas)

Get started analysing these datasets using Python:

```python
import pandas as pd

# Load datasets
customer = pd.read_csv('https://raw.githubusercontent.com/Fen-Pang/Capstone-Market-Analysis/main/customer.csv')
purchase = pd.read_csv('https://raw.githubusercontent.com/Fen-Pang/Capstone-Market-Analysis/main/purchase.csv')

# Check datasets
print(customer.shape)
print(purchase.shape)

# Convert dates
purchase['order_date'] = pd.to_datetime(purchase['order_date'], format='%d/%m/%Y')
purchase['shipping_date'] = pd.to_datetime(purchase['shipping_date'], format='%d/%m/%Y')
```

## 💡 Key Findings from Python Analysis
Based on the analysis in Google Colab:
1. Sales Trends: Total actual sales revenue was approximately $263.69 million. Monthly sales were mostly around $6 to $7 million.
2. Product Sales: Curtains generated the highest revenue ($18.62 million), while Sports Shoes had the highest quantity sold (9,642 units).
3. Customer Demographics: Male customers generated slightly higher sales than female customers. Customers aged 51 had the highest average spending per purchase.
4. High Value Customers: Customer CS00609 recorded the highest total spending ($446,568.14).
5. Sales by Country: Highest is Colombia ($74.37 million) and lowest is Brazil ($60.79 million).

## 📊 Power BI Dashboard – Descriptive Analytics
Dashboard 1: Sales & Product Performance
This dashboard focuses on Research Objectives 1, 2 and 5. It shows monthly sales trends, best-selling products by revenue and quantity sold, and sales performance across different countries.

Key Observations:
- Total sales revenue was approximately $263.69 million.
- Curtains generated the highest revenue ($18.62 million), while Sports Shoes had the highest quantity sold (9,642 units).
- Colombia recorded the highest sales revenue ($74.37 million), while Brazil recorded the lowest ($60.79 million).

These findings help identify strong-performing products and markets, supporting decisions on product strategies and sales opportunities.
[Dashboard 1 Screenshot – To Be Added]

Dashboard 2: Customer Analysis
This dashboard focuses on Research Objectives 3 and 4. It compares customer spending by gender and age, and identifies the top 10 customers based on total spending.

Key Observations:
- Male customers generated slightly higher total sales than female customers.
- Customers aged 51 had the highest average spending per purchase.
- Customer CS00609 recorded the highest total spending ($446,568.14).

These findings help identify valuable customer groups and high-spending customers who may be suitable for targeted marketing and retention strategies.

[Dashboard 2 Screenshot – To Be Added]

## 🛠️ Tools Used
1. Python (Google Colab) – Data cleaning, combining datasets, data analysis and charts.
2. Power BI – Creating interactive dashboards to analyse sales, customers and products.
3. GitHub – Storing project files, documentation and tracking project progress.
