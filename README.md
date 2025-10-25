# Retail Transactions Data Analysis

## Overview

This project performs **data preprocessing** and **visualization** on a retail transactions dataset (`Retail_Transactions_2000.csv`) to understand customer demographics, purchasing behavior, and revenue trends.

The analysis includes:

* Cleaning and validating transaction data
* Encoding categorical variables
* Scaling numerical features
* Visualizing distributions, trends, and relationships between key variables
* Generating a **heatmap of product category vs payment mode** to analyze total sales

---

## Dataset Description

The dataset contains 2000 retail transactions with the following columns:

| Column          | Description                                       |
| --------------- | ------------------------------------------------- |
| TransactionID   | Unique transaction identifier                     |
| CustomerID      | Unique customer identifier                        |
| Gender          | Customer gender (`Male`, `Female`, `Other`)       |
| Age             | Customer age                                      |
| City            | Customer city                                     |
| ProductCategory | Category of the purchased product                 |
| Quantity        | Number of items purchased                         |
| Price           | Price per unit                                    |
| PurchaseDate    | Transaction date                                  |
| PaymentMode     | Mode of payment (`Cash`, `Card`, `Wallet`, `UPI`) |
| TotalAmount     | Total amount paid (Quantity × Price)              |

---

## Part A: Data Preprocessing

1. **Loading the dataset:**

   * Read the CSV file using `pandas`.

2. **Initial exploration:**

   * Inspect dataset shape, size, null values, duplicates, and data types.
   * Check basic statistics with `describe()` and unique values for categorical columns.

3. **Data cleaning:**

   * Verified `Quantity`, `Price`, `Age`, and `TotalAmount` for invalid values.
   * Removed duplicate `TransactionID`s.
   * Standardized categorical text columns (`Gender`, `City`, `PaymentMode`).

4. **Feature engineering:**

   * Created `CheckAmount = Quantity × Price` to validate `TotalAmount`.
   * Extracted `PurchaseMonth` and `PurchaseDayOfWeek` from `PurchaseDate`.
   * Created `AgeGroup` categorical bins: `18-25`, `26-40`, `41-60`, `60+`.

5. **Encoding & scaling:**

   * Dropped `TransactionID` and `CustomerID` (no predictive value).
   * Applied one-hot encoding for `City`, `ProductCategory`, `PaymentMode`, `AgeGroup`.
   * Label encoded all boolean and object columns.
   * Min-max scaled numerical columns for consistent range.

6. **Saved cleaned dataset:**

   * Exported cleaned data as `Retail_Cleaned.csv`.

---

## Part B: Data Visualization

1. **Customer demographics:**

   * Age distribution histogram with KDE.
   * Gender distribution count plot.
   * Top 10 cities by number of customers.

2. **Product and sales insights:**

   * Top 10 product categories by customer count.
   * Monthly sales trend line chart.
   * Payment mode distribution pie chart.
   * Average spend per customer by age group.
   * City-wise revenue contribution bar chart.

3. **Heatmap: Product Category vs Payment Mode**

   * A heatmap showing **total sales amount (₹)** for each combination of product category and payment mode.
   * Helps identify which payment modes are most used for each product category and their revenue impact.

---

## Dependencies

Python packages used:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
