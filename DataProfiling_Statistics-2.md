# 📊 Data Profiling & Statistics (Step 2)

## 📌 Overview
After establishing initial data connections and completing basic header transformations, the next essential phase is **Data Profiling, Quality Assessment, and Descriptive Analysis**. Using Power Query's built-in data profiling tools, this step evaluates completeness, uniqueness, value distributions, and statistical metrics to surface hidden data quality issues before building downstream models.

---

## 🛠️ Step-by-Step Data Profiling & Quality Analysis

### 1️⃣ Enabling Power Query Profiling Tools & Full Dataset Evaluation
- Navigated to the **View** tab in Power Query Editor to enable **Column Quality**, **Column Distribution**, and **Column Profile** features.
- Switched the profiling scope from the default top 1,000 rows to **Column profiling based on entire dataset** in the status bar to guarantee statistical accuracy across all 1,828 records.

![Selecting Profiling Views](./images_laborStatistics/SelectColumnProfile.jpg)  
*Figure 2.1: Enabling Data Profiling views in Power Query Editor.*

![Profiling Entire Dataset](./images_laborStatistics/ProfileEntireDataSet.jpg)  
*Figure 2.2: Expanding profiling scope to analyze all dataset records.*

---

### 2️⃣ Profiling Data Completeness, Nulls, & Uniqueness
- Inspected the top quality bars and value distributions across key primary keys and foreign keys.
- **Null & Error Auditing:** Verified 0 errors and 0 empty values across profiled core fields such as `Order Date` and `Product ID`.
- **Uniqueness & Distinct Analysis:**
  - `Product ID`: Contains **256 distinct values** and **21 unique values** (values appearing exactly once) across 1,828 rows.
  - `Order Date`: Contains **552 distinct dates** spanning from `1/3/2021` to `12/31/2023`, with an average date distribution centered around `8/6/2022`.

![Product ID Uniqueness Profiling](./images_laborStatistics/ClickProductID.jpg)  
*Figure 2.3: Initial uniqueness and distinct value assessment for Product ID.*

![Detailed Product ID Statistics](./images_laborStatistics/ProductIDStatistics.jpg)  
*Figure 2.4: Comprehensive column statistics and value distribution tree for Product ID.*

![Date Statistics Profile](./images_laborStatistics/DateStatistics.jpg)  
*Figure 2.5: Temporal distribution and key metric summary for Order Date.*

---

### 3️⃣ Descriptive Statistics & Metric Distributions

- **Numerical Field Profiling (`Sales`):**
  - Selected the `Sales` column to analyze central tendency, dispersion, and extreme values.
  - **Count:** 1,828 valid entries with 0 errors and 0 missing values.
  - **Range:** Minimum sale of `$2.99` up to a maximum sale of `$899.879`.
  - **Distribution:** Identified significant value skewness, where the single most frequent sales price point (`$119.95`) accounts for **47 rows (2%)** of total volume.

![Selecting Sales Column for Profiling](./images_laborStatistics/ClickSalesColumn.jpg)  
*Figure 2.6: Selecting numerical metric columns for descriptive statistical breakdown.*

![Sales Value Skew and Frequency](./images_laborStatistics/FortySevenPercentsales.jpg)  
*Figure 2.7: Statistical range and high-frequency value peaks within Sales.*

---

### 4️⃣ Categorical & Frequency Distribution Analysis

- **Top Performing Category Items:**
  - Analyzed individual item row counts using the value distribution histogram.
  - Identified `SP-S-6604` as the top product line by transaction volume, representing **64 total rows (3%)** of the overall dataset.

![Top Volume Product Identification](./images_laborStatistics/MaxProduct.jpg)  
*Figure 2.8: Frequency distribution highlighting top transaction product IDs.*

![Product with Maximum Rows Details](./images_laborStatistics/ProductWithMaxNbrRows.jpg)  
*Figure 2.9: Focused breakdown of peak transaction volume for product SP-S-6604.*

- **Low-Frequency & Tail Items:**
  - Examined low-occurrence product entries to check for potential data fragmentation or orphaned SKUs.
  - Filtered items at the low end of the spectrum (such as `FW-Y-4233`), each accounting for **10 rows (< 1%)**.

![Low Volume Tail Profiling](./images_laborStatistics/LeastNumberOfRows10.jpg)  
*Figure 2.10: Identifying low-frequency records and tail distributions.*

---

## 🚨 Summary of Data Quality Findings

- **Zero Completeness Issues:** Data completeness is high across core transaction fields with **0% missing values** and **0% error rates**.
- **High Cardinality:** Key dimensions like `Product ID` show healthy cardinality distribution (**256 distinct values** out of 1,828 records) suitable for relational modeling.
- **Balanced Date Span:** Historical transactions cover a multi-year window (`2021` to `2023`) with smooth date distributions and peak volume days (e.g., `12/3/2022` with 20 transactions).

---

## 🔗 Related Links & Steps

* ⬅️ **Previous Step:** [1️⃣ Connect Data & Reformat Columns](./ConnectData_Reformat_Headers_columns-1.md)
* ➡️ **Next Step:** [3️⃣ Custom Functions (Advanced Query Editor)](./query_advanced_editor_customFun-3.md)
* 🏠 **Main Repository:** [Power BI Analysis Repo](https://github.com/yourexodus/mfrancis_PowerBI_Analysis)
