# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

Retail businesses rely on accurate and consistent data to make informed decisions. However, the raw dataset provided for this assignment contained several data quality issues, including inconsistent text formatting, missing values, duplicate order IDs, date inconsistencies, and records that did not satisfy the given business rules. These issues could lead to incorrect reporting and unreliable business insights.

The objective of this project was to clean and validate the dataset, apply the required business rules, create an analysis-ready version of the data, and generate summary reports that accurately represent the business performance.

---

# Dataset Description

The dataset contains retail order information at the order level. It includes customer details, product categories, sales and profit values, discounts, shipping information, payment status, and order status.

Two versions of the dataset are included in this repository:

* **raw_orders.xlsx** – The original dataset provided for the assignment. This file has been kept unchanged.
* **cleaned_orders.xlsx** – The cleaned version of the dataset after applying all required data cleaning, validation, and calculated fields.

Additional files included in this repository are:

* **data_quality_report.xlsx**
* **pivot_summary.xlsx**
* **cleaning_log.md**

---

# Tools Used

The project was completed using the following tools and spreadsheet features:

* Excel
* Spreadsheet formulas such as TRIM, PROPER, IF, IFERROR, COUNTIF, YEAR, MONTH, TEXT, and other logical functions
* Conditional Formatting
* Find and Replace
* Pivot Tables
* Sorting and Filtering

---

# Cleaning Steps Performed

The dataset was cleaned in a structured manner to ensure that the original data remained unchanged while producing a reliable version for analysis.

The following steps were performed:

1. Preserved the original dataset as **raw_orders.xlsx**.
2. Created a separate working file named **cleaned_orders.xlsx**.
3. Removed leading, trailing, and extra spaces from text fields.
4. Standardized capitalization and corrected inconsistent text values across customer names, regions, states, cities, categories, sub-categories, ship modes, payment status, and order status.
5. Standardized the order and ship date columns into a consistent date format.
6. Identified missing values throughout the dataset.
7. Replaced missing Region values with **"Unknown"**.
8. Replaced missing Ship Mode values with **"Unknown"**.
9. Replaced missing Discount values with **0** where allowed by the business rules.
10. Identified duplicate Order IDs and flagged conflicting records instead of deleting them.
11. Flagged records where the ship date occurred before the order date.
12. Created additional calculated columns:

* Cleaned Discount
* Calculated Sales
* Calculated Profit
* Profit Margin
* Shipping Delay Days
* Order Month
* Order Year
* Data Quality Flag

13. Generated a Data Quality Report summarizing all identified issues.
14. Created Pivot Tables to summarize and analyse the cleaned data.

---

# Business Rules Applied

The following business rules were applied while cleaning the dataset:

* Missing Region values were replaced with **Unknown** and recorded in the data quality report.
* Missing Ship Mode values were replaced with **Unknown**.
* Missing Discount values were treated as **0** only when the remaining sales-related information was valid.
* Negative discount values and discounts above the accepted range were flagged as invalid.
* Orders where the Ship Date occurred before the Order Date were marked as invalid shipping records.
* Cancelled orders, failed payments, and refunded transactions were excluded from completed sales summaries.
* Exact duplicate rows were removed only if every value matched.
* Duplicate Order IDs containing conflicting information were retained and flagged for manual review instead of being deleted.

---

# Summary of Data Quality Issues Found

Several data quality issues were identified during the cleaning process, including:

* Missing Region values
* Missing Ship Mode values
* Missing Discount values
* Missing Order Dates
* Missing Ship Dates
* Duplicate Order IDs with conflicting information
* Invalid shipping dates
* Invalid discount values
* Cancelled orders
* Failed payment records
* Refunded transactions
* Records requiring manual review

All identified issues have been documented in **data_quality_report.xlsx**.

---

# Summary of Final Pivot Reports

After cleaning the dataset, the following Pivot Tables were created to summarize business performance:

1. **Sales and Profit by Region** – compares business performance across different regions.
2. **Sales and Profit by Category and Sub-category** – identifies product categories contributing the highest sales and profit.
3. **Order Count by Ship Mode** – shows the number of orders handled by each shipping method.
4. **Average Profit Margin by Customer Segment** – compares profitability across customer segments.
5. **Refunded, Cancelled, and Failed Orders by Region** – highlights non-completed transactions across different regions.
6. **Monthly Sales Trend** – displays sales performance over time.

Sorting and filtering were applied to selected Pivot Tables to improve readability and analysis.

---

# Key Business Insights

The cleaned dataset provided a clearer view of overall business performance. Some important observations include:

* Sales and profit are not evenly distributed across all regions, indicating regional differences in business performance.
* Certain product categories contribute significantly more revenue and profit than others.
* Standard shipping is the most frequently used shipping method.
* A small number of records require manual review because of conflicting duplicate Order IDs.
* Excluding cancelled, refunded, and failed transactions provides a more accurate representation of completed sales.
* Cleaning and validating the data improves the reliability of business reports and future analysis.

---

# Assumptions and Limitations

## Assumptions

* Missing Discount values were treated as **0** only when the remaining sales information was valid.
* Quantity and Unit Price values were assumed to be correct for calculation purposes.
* Duplicate Order IDs containing conflicting information were considered business exceptions and therefore retained for manual review.
* Calculated fields were created using the information available in the provided dataset.

## Limitations

* Some records still require manual verification because conflicting duplicate Order IDs cannot be resolved automatically.
* The analysis depends entirely on the accuracy of the original source data.
* Some business decisions were based on the assignment instructions because additional business documentation was not provided.

---

# Screenshots Included

The repository includes screenshots that demonstrate the work completed during the assignment:

* **raw_data_preview.png** – Original dataset before any cleaning was performed.
* **cleaned_data_preview.png** – Cleaned dataset showing standardized fields and calculated columns.
* **pivot_summary_1.png** – Sales and Profit by Region Pivot Table.
* **pivot_summary_2.png** – Monthly Sales Trend Pivot Table.

These screenshots provide evidence of the data cleaning process and the final analytical outputs generated from the cleaned dataset.
