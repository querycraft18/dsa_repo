**Data Cleaning and Exploratory Data Analysis**



**Project Overview**

This project focuses on cleaning and analyzing customer, order, product, payment, return, and shipment datasets using Python.



**Objectives**

Identify duplicate records.

Check for missing values and invalid data.

Apply business rules to identify inconsistent records.

Prepare clean datasets for analysis.

Answer exploratory data analysis (EDA) questions.



**Tools Used**

Python

Jupyter Notebook

Pandas

NumPy

Git and GitHub



**Exploratory Data Analysis Questions and Findings**

1. **Which sales channel generates the highest gross revenue?**

Findings: 

Web generated the highest gross line revenue among the three sales channels, exceeding Marketplace by ₱12,068.41. However, gross revenue alone does not indicate which channel is the most profitable.



**2. Which product category generates the highest gross revenue?**

Findings:

Toys generated the highest gross line revenue among the product categories, exceeding Electronics by ₱23,428.91. Electronics had the most line items, with 5,045, showing that the category with the most line items is not necessarily the one with the highest revenue.



**3. Which payment method is most common?**

Findings:

Credit Card was the most frequently recorded payment method, with 3,137 records. This measures usage frequency, not the total amount paid through each method.



**4. What return reason occurs most often?**

Findings:

Changed mind was the most frequently recorded return reason, appearing in 182 return records. However, return frequency alone does not show which reason causes the greatest financial loss or operational impact.



**5. Which courier handles the most shipments?**

Findings: J\&T handled the highest shipment volume, with 3,042 shipments. However, a higher shipment volume does not necessarily indicate better delivery quality; on-time delivery rates, delays, and failed deliveries should also be evaluated.



**Data Cleaning Decisions Documentation**



**1. REMOVING DUPLICATE RECORDS**

**What changed:** Removed exact duplicate rows from the original tables to create cleaned DataFrames using drop\_duplicates().

**Why:** Duplicate records can inflate record counts and distort sales and customer analysis.

**How it was verified:** Counted duplicate rows before and after cleaning.



**2. FLAGGING INVALID CUSTOMER AGES**

**What changed:** Flagged customer records with negative ages, ages below 18, or other invalid values based on the defined business rules.

**Why:** Invalid ages may affect customer segmentation and analysis.

**How it was verified:** Counted and inspected records that violated the rules.



**3. FLAGGING INVALID ORDER QUANTITIES**

**What changed:** Identified order items with zero or negative quantities.

**Why:** Invalid quantities can distort revenue and cost calculations.

**How it was verified:** Counted invalid quantities and inspected affected records.



**4. CLEANING CURRENCY VALUES**

**What changed:** Converted purchase price values into numeric format using the clean\_currency() function.

**Why:** Currency symbols and inconsistent formats may prevent accurate mathematical calculations.

**How it was verified:** Inspected the converted values and checked their data type.



**5. FLAGGING INCONSISTENT REFUND RECORDS**

**What changed:** Flagged records where refunded\_flag and refund\_amount do not agree.

**Why:** Conflicting refund information may affect refund reporting and financial analysis.

**How it was verified:** Counted and inspected records with conflicting combinations.



**6. CHECKING MISSING CUSTOMER REFERENCES**

**What changed:** Identified orders whose customer IDs do not exist in the cleaned customers table.

**Why:** Missing customer matches can affect customer-level analysis.

**How it was verified:** Counted the unmatched customer IDs and inspected the orders.



**7. CHECKING MISSING PRODUCT REFERENCES**

**What changed:** Identified order items whose product IDs do not match records in the products table.

**Why:** Missing product matches can affect product category, cost, and profitability analysis.

**How it was verified:** Used a left merge with an indicator to identify unmatched rows.







