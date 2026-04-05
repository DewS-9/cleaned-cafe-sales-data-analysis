# Coffee Shop Sales Data Cleaning and Analysis

## Overview
This project focuses on cleaning and analyzing a messy coffee shop transaction dataset. 
The goal was to transform inconsistent raw data into a reliable dataset and get meaningful business insights.

---

## Dataset Description
The dataset contains 10,000 transactions with the following columns:
- Transaction ID
- Item
- Quantity
- Price Per Unit
- Total Spent
- Payment Method
- Location
- Transaction Date

---

## Data Cleaning

### Handling Missing and Inconsistent Values
- Standardized inconsistent missing values (`UNKNOWN`, `ERROR`, `NaN`) for systematic processing
- Converted `Quantity`, `Price Per Unit`, and `Total Spent` to numeric using `pd.to_numeric(errors="coerce")`
- Leveraged relationships between columns:
  - Filled missing `Total Spent` using:  
    **Quantity × Price Per Unit**
  - Filled missing `Quantity` using:  
    **Total Spent ÷ Price Per Unit**
- Estimated missing `Item` and `Price Per Unit` values using item-level consistency
- Imputed missing values in `Payment Method` and `Location` using mode (low percentage of missing data)
- Converted `Transaction Date` to datetime and removed invalid entries
- Removed rows with missing dates (~4.6%) to preserve temporal accuracy

---

## Data Validation
- Verified consistency of calculated fields:
  - Ensured **Total Spent = Quantity × Price Per Unit**
- Checked for:
  - Negative or impossible values
  - Duplicate records
- Confirmed correct data types for all columns
- Reset index after cleaning

---

## Data Analysis

### Objectives
- Identify top-selling products
- Analyze revenue distribution
- Understand customer behavior patterns

---

## Key Insights
- Sandwich is the most sold item by quantity
- Sandwich generates the highest overall revenue
- Sales remain relatively consistent over time
- Takeaway orders contribute the majority of revenue
- Digital Wallet is the most frequently used payment method
- Items, Salad, and Smoothie generate higher revenue despite lower sales volume, indicating pricing impact

---

## Conclusion
The dataset was successfully cleaned and validated to ensure reliability. 
The analysis provides insights into product performance, sales trends, and customer behavioral patterns. This can be used to manage products, optimize sales, and improve customer service. 
