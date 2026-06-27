# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

The objective of this project was to clean and validate a retail order dataset containing various data quality issues. The raw data included missing values, inconsistent text formatting, duplicate order IDs, date inconsistencies, and invalid records that could affect business reporting. The goal was to create a clean, analysis-ready dataset and generate summary reports to support business decision-making.

---

## Dataset Description

The dataset contains order-level information for a retail business, including customer details, product categories, sales, profit, shipping information, discounts, payment status, and order status.

Two versions of the dataset are included in this repository:

* **raw_orders.xlsx** – Original dataset provided for the assignment (unchanged).
* **cleaned_orders.xlsx** – Cleaned dataset containing standardized values, calculated fields, and data quality flags.

---

## Tools Used

* Google Sheets / Microsoft Excel
* Excel formulas (TRIM, PROPER, IF, IFERROR, COUNTIF, YEAR, MONTH, TEXT, etc.)
* Pivot Tables
* Conditional Formatting
* Find & Replace

---

## Cleaning Steps Performed

The following steps were carried out to prepare the dataset for analysis:

* Preserved the original dataset without making any modifications.
* Removed unnecessary leading and trailing spaces from text fields.
* Standardized capitalization and corrected inconsistent text entries.
* Cleaned and standardized customer names, regions, states, cities, categories, sub-categories, ship modes, payment statuses, and order statuses.
* Converted date fields into a consistent format.
* Calculated shipping delay for each order.
* Filled missing Region and Ship Mode values with **"Unknown"**.
* Replaced missing Discount values with **0** where applicable according to the business rules.
* Identified duplicate Order IDs and flagged records containing conflicting information.
* Added calculated columns including:

  * Cleaned Discount
  * Calculated Sales
  * Calculated Profit
  * Profit Margin
  * Shipping Delay Days
  * Order Month
  * Order Year
  * Data Quality Flag
* Generated a data quality report and pivot summary report.

---

## Business Rules Applied

The following business rules were followed during the cleaning process:

* Missing Region values were replaced with **Unknown**.
* Missing Ship Mode values were replaced with **Unknown**.
* Missing Discount values were treated as **0** only when other sales-related fields were valid.
* Negative or unusually high discount values were flagged as invalid.
* Records where the ship date occurred before the order date were flagged.
* Cancelled, refunded, and failed payment records were excluded from completed sales summaries.
* Duplicate Order IDs containing different information were retained and flagged for manual review instead of being removed.

---

## Summary of Data Quality Issues Found

The following issues were identified during data validation:

* Missing values in Region, Ship Mode, Discount, Order Date, and Ship Date.
* Inconsistent text formatting across several columns.
* Duplicate Order IDs with conflicting information.
* Invalid shipping dates.
* Invalid or missing discount values.
* Records with cancelled, refunded, or failed payment statuses.
* Data requiring manual review before final business reporting.

---

## Summary of Pivot Reports

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-category
3. Order Count by Ship Mode
4. Average Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

Sorting and filtering were applied to selected pivot tables to improve readability and analysis.

---

## Key Business Insights

The cleaned dataset made it easier to identify business trends and data quality issues. Some key observations include:

* Sales performance varied across different regions.
* Certain product categories generated higher profits than others.
* Standard shipping was the most frequently used shipping method.
* A small number of records required manual review due to conflicting Order IDs.
* Cancelled, refunded, and failed transactions represented non-completed business and were excluded from completed sales analysis.
* Data cleaning significantly improved the consistency and reliability of the dataset for reporting.

---

## Assumptions and Limitations

### Assumptions

* Blank discount values were treated as **0** when other sales information was available.
* Quantity and Unit Price values were assumed to be accurate.
* Duplicate Order IDs containing different information were assumed to require manual verification.
* Profit Margin was calculated as **Profit ÷ Sales**.

### Limitations

* Some business rules required reasonable assumptions because detailed business documentation was not provided.
* Records with conflicting duplicate information cannot be resolved automatically.
* The accuracy of calculated fields depends on the correctness of the original dataset.

---

## Repository Structure

```text
part1_data_cleaning/
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
└── README.md
```

---

## Screenshots Included

The repository contains the following screenshots as evidence of the completed work:

* **raw_data_preview.png** – Original dataset before cleaning.
* **cleaned_data_preview.png** – Cleaned dataset with calculated columns.
* **pivot_summary_1.png** – Sales and Profit by Region pivot table.
* **pivot_summary_2.png** – Monthly Sales Trend (or another pivot summary).

These screenshots demonstrate the cleaning process and the final analysis outputs.
