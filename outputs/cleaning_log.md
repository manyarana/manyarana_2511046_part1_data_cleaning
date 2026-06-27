# Cleaning Log

## Part 1: Business Data Cleaning, Validation & Excel Reporting

### List of Issues Found

After reviewing the raw dataset, I identified several data quality issues that could affect the accuracy of the analysis. These included:

* Extra spaces and inconsistent capitalization in text fields.
* Missing values in **Region**, **Ship Mode** and **Discount**.
* Inconsistent formatting of text and date fields.
* Duplicate **Order ID** values containing conflicting information.
* Ship dates that occurred before the corresponding order dates.
* Records with cancelled orders, returned orders, and failed or refunded payments.
* Missing discount values and a few records requiring additional validation.

---

## Cleaning Actions Performed

To prepare the dataset for analysis, the following cleaning steps were completed:

* Preserved the original dataset as **raw_orders.xlsx** without making any changes.
* Created a separate cleaned version named **cleaned_orders.xlsx**.
* Removed unnecessary leading and trailing spaces from text fields.
* Standardized capitalization using spreadsheet functions such as **TRIM**, **PROPER**, and **Find & Replace**.
* Standardized values in the following columns:

  * Customer Name
  * Segment
  * Region
  * State
  * City
  * Category
  * Sub-category
  * Ship Mode
  * Payment Status
  * Order Status
* Converted the order and ship dates into a consistent date format.
* Calculated the shipping delay for every order.
* Replaced missing Region and Ship Mode values with **"Unknown"**.
* Filled missing Discount values with **0** where appropriate according to the business rules.
* Added calculated columns for cleaned discount, calculated sales, calculated profit, profit margin, shipping delay, order month, order year, and data quality status.
* Generated a data quality report and pivot summary report for business analysis.

---

## Business Rules Applied

The following business rules were applied during the cleaning process:

* Missing **Region** values were replaced with **"Unknown"** and recorded in the data quality report.
* Missing **Ship Mode** values were replaced with **"Unknown"** and documented.
* Missing discount values were treated as **0** only when the remaining sales-related fields were valid.
* Records with negative or invalid discount values were marked for review.
* Orders where the ship date occurred before the order date were flagged as invalid shipping records.
* Cancelled orders, failed payments, and refunded transactions were excluded from completed sales summaries.
* Duplicate Order IDs containing different information were retained and marked for manual review instead of being deleted.

---

## Assumptions Made

The following assumptions were made while cleaning the data:

* Blank discount values were considered to represent **0% discount** when the rest of the record contained valid sales information.
* Profit margin was calculated as **Profit ÷ Sales**.
* Quantity and Unit Price values were assumed to be accurate for calculating sales.
* Duplicate Order IDs with conflicting information were treated as potential business issues rather than duplicate entries.

---

## Records Removed

* 47 exact duplicate rows were found, so 47 records were removed.
* Duplicate Order IDs with conflicting values were retained for further review.

---

## Records Flagged

The following records were flagged during the cleaning process:

* Duplicate Order IDs containing conflicting information.
* Records where the ship date was earlier than the order date.
* Records with invalid discount values.
* Records containing missing or incomplete critical information.
* Records where Region or Ship Mode had been replaced with **"Unknown"**.

---

## Limitations

Although the dataset was cleaned and validated carefully, a few limitations remain:

* Some business rules required reasonable assumptions because detailed business documentation was not provided.
* Records with conflicting duplicate Order IDs require manual verification before any final business decision can be made.
* The accuracy of calculated fields depends on the correctness of the original Quantity, Unit Price, Sales, and Profit values.
* The cleaning process was based entirely on the information available in the provided dataset and spreadsheet tools.
