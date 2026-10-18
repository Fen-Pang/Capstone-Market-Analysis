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
5. Analyse customers' annual spending patterns to understand purchasing behaviour and identify sales opportunities.

<h1>Retail Customer and Purchase Datasets📊</h1>

This repository contains two datasets, customer.csv and purchase.csv, covering customer demographics, purchasing behaviour and retail product sales transactions. It include customer information such as age, gender, income and country, alongside purchase details such as product names, prices, quantities, order dates and shipping costs.

These datasets support exploratory data analysis (EDA), sales performance analysis, customer segmentation, product performance evaluation and predictive analytics to identify high-value customers and opportunities to increase retail sales.

<img width="1317" height="742" alt="image" src="https://github.com/user-attachments/assets/fd2d0b2f-b7d0-4953-8c8b-868132c2485a" />

## 📋 Dataset Overview

* **File Name:** `customer.csv and purchase.csv`
* **Time Horizon:** TBA YYYY - TBA YYYY
* **Target Category:** Retail Customer Purchases
* **Key Entities:** Customer Demographics, Purchase Transactions, Product Sales, Revenue and Customer Spending

  Link to Jupyter Notebook in Google Colab: To be added later
   
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

## 🔍 Data Quality & Cleaning Notes (To be updated)

If you are using this dataset for data cleaning projects, please note that it intentionally contains realistic real-world data anomalies:
* **Missing Values (NaNs):** Features like `Region`, `Salesperson`, `Unit_Price`, `Discount`, and `Sales` contain scattered missing fields (e.g., missing revenue values or unattributed regional boundaries).
* **Calculated Columns:** The `Sales` column follows the general formula:  
  \[\text{Sales} = (\text{Quantity} \times \text{Unit\_Price}) \times (1 - \text{Discount})\]
  This relationship can be exploited to programmatically restore missing metrics.
* **Empty Rows:** The raw structure contains blank structural divider rows (`,,,,,,,,,`) that should be filtered out during preprocessing.

## 🛠️ Usage Example (Python & Pandas) (To be updated)

Get started analyzing this dataset quickly using Python:

```python
import pandas as pd

# Load the dataset and drop completely empty structural lines
df = pd.read_csv('sales_data.csv').dropna(how='all')

# Convert date column to datetime object
df['Date'] = pd.to_datetime(df['Date'])

# Quick view of total sales revenue by product
revenue_by_product = df.groupby('Product')['Sales'].sum().sort_values(ascending=False)
print("Revenue by Product:\n", revenue_by_product)
```

## 💡 Potential Projects & Analysis Directions (To be updated)
1. **Sales Performance Dashboards:** Create interactive Tableau or Power BI visualizations mapping regional performance by salesperson.
2. **Predictive Modeling:** Build machine learning regression models to predict expected order values or customer quantity demands.
3. **Discount Impact Studies:** Assess whether offering a $10\%$ vs $15\%$ discount yields a statistically significant increase in total items sold.

## 🛠️ Tools Used
1. Python (Google Colab) – Data cleaning, combining datasets, data analysis, charts and predictive modelling.
2. Power BI – Creating interactive dashboards to analyse sales, customers and products.
3. GitHub – Storing project files, documentation and tracking project progress.
