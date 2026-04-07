# Coffee Shop Sales Data Cleaning and Analysis

## Overview
This project focuses on cleaning and analyzing a messy coffee shop transaction dataset. 
The goal was to transform inconsistent, messy data into a reliable dataset and get impactful business insights.

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
<img width="742" height="653" alt="image" src="https://github.com/user-attachments/assets/17f5aeff-c64b-472b-9ef5-1594501b4c82" />
<img width="742" height="656" alt="image" src="https://github.com/user-attachments/assets/dd557bef-546c-4cd0-87ef-9f0745448c92" />

- Sandwich dominates both quantity and revenue, indicating strong demand and pricing advantage.
- Items, Salad, and Smoothie generate higher revenue despite lower sales volume, indicating pricing impact
  
<img width="1323" height="414" alt="image" src="https://github.com/user-attachments/assets/c9f8a774-12ff-4a09-945b-67b934e24374" />

- There are high revenues during January, May, June, August, and November. Revenues drop significantly from mid July to the beginning of August and from the end of September to mid-October. This shows a significant seasonal impact
- Overall, sales remain generally stable, with noticeable seasonal fluctuations during specific periods.

<img width="756" height="659" alt="image" src="https://github.com/user-attachments/assets/12b146c8-ea49-4691-8d09-dd1a3f58674f" />

- Takeaway orders contribute the majority of revenue, suggesting a stronger demand for takeaway services compared to in-store dining.

<img width="741" height="680" alt="image" src="https://github.com/user-attachments/assets/283cee0d-244b-4753-b434-b6977637853a" />
<img width="753" height="690" alt="image" src="https://github.com/user-attachments/assets/cb591105-f9a3-4573-a100-b736138ba4a9" />

- Digital Wallet is the most frequently used payment method, indicating a preference for online transactions. 

---

## Conclusion
The dataset was successfully cleaned and validated to ensure reliability. 
The analysis provides insights into product performance, sales trends, and customer behavioral patterns. This can be used to manage products, optimize sales, and improve customer service.

---

## Recommendations

- Increase inventory for high-performing items like the Sandwich
- Introduce more sandwich options
- Promote underperforming items to improve sales balance
- Update the menu during low-revenue seasons to minimize the revenue drops.
- Expand digital payment options due to high usage
- Improve the interior of the store to attract more In-Store customers.

---

## Limitations

- Some missing values were imputed using statistical methods, which may introduce minor bias
- Removed date entries (~4.6%) may slightly affect time-based analysis
