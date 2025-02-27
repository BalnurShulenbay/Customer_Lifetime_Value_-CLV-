# Customer Lifetime Value Analysis

## Overview
This project analyzes customer purchasing behavior and predicts customer lifetime value (CLV) using the Online Retail dataset. By understanding purchase patterns and predicting future customer value, businesses can optimize marketing strategies and improve customer retention.

## Purpose & CLV Explanation
The primary goal of this code is to predict how much revenue a customer will generate in the future (specifically, the next 3 months) based on their past purchasing behavior. 

Customer Lifetime Value (CLV) is a metric that estimates the total revenue a business can expect from a single customer throughout their relationship. This analysis:

1. Identifies patterns in customer purchasing behavior using RFM (Recency, Frequency, Monetary value) analysis
2. Creates features from past 3-month intervals to predict future spending
3. Builds a predictive model that allows businesses to identify high-value customers worth investing in
4. Provides insights about which behavioral factors most strongly indicate future spending potential

By accurately predicting CLV, businesses can make informed decisions about customer acquisition costs, retention strategies, and personalized marketing campaigns.

## Features
- Data cleaning and preparation for retail transaction data
- RFM (Recency, Frequency, Monetary) analysis
- Customer purchase pattern visualization
- 3-month CLV prediction using linear regression

## Data Source
The dataset is publicly available and sourced from the UCI Machine Learning Repository. It contains real-world transaction data from a UK-based online retail company selling unique all-occasion gifts. The data can be accessed from:
- GitHub: https://github.com/rajeevratan84/datascienceforbusiness/master/OnlineRetail.xlsx
- Original Source: [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)

## Data Types
The dataset includes the following fields:

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| InvoiceNo | String | A 6-digit integral number uniquely assigned to each transaction |
| StockCode | String | A 5-digit integral number uniquely assigned to each distinct product |
| Description | String | Product name description |
| Quantity | Numeric | Number of items purchased |
| InvoiceDate | Datetime | Date and time when the transaction occurred |
| UnitPrice | Numeric | Product price per unit in sterling pounds (£) |
| CustomerID | Numeric | A 5-digit integral number uniquely assigned to each customer |
| Country | String | Name of the country where the customer resides |

## Analysis Steps
1. **Data Preparation**
   - Remove negative quantities (likely returned items)
   - Remove blank customer IDs
   - Filter transactions to include only those before December 2011
   - Calculate sales revenue

2. **Customer Purchase Summary**
   - Group data by customer and invoice
   - Calculate key metrics per customer:
     - Min/max/total sales
     - Average purchase value
     - Number of purchases
     - Purchase duration
     - Average frequency between purchases

3. **Visualization**
   - Distribution of purchase counts
   - Average days between purchases

4. **CLV Prediction**
   - Segment data into 3-month intervals
   - Create RFM features based on customer behavior
   - Split data into training and testing sets
   - Build linear regression model to predict future customer value

## Model Performance
- In-Sample R-Squared: 0.5851
- Out-of-Sample R-Squared: 0.8042
- In-Sample MSE: 199.3392
- Out-of-Sample MSE: 197.8790

## Requirements
- pandas
- matplotlib
- scikit-learn

## Usage
```python
# Clone the repository
git clone https://github.com/yourusername/customer-lifetime-value-analysis.git

# Install dependencies
pip install pandas matplotlib scikit-learn

# Run the Jupyter notebook
jupyter notebook Customer_Lifetime_Value_Analysis.ipynb
```

## Key Insights
- Recent purchase behavior is strongly predictive of future spending
- Purchase frequency in the most recent periods has the highest positive coefficient
- The model performs well on unseen data, with an R-squared of 0.80
