# 📊 Data Profiling & Statistics (Step 2)

## 📌 Overview
After loading and reformatting the initial dataset, the next critical phase in the ETL pipeline is **Data Profiling and Statistical Assessment**. This step ensures data quality, identifies missing or anomalous values, checks column distributions, and verifies dataset integrity prior to building custom functions and applying advanced data shaping.

---

## 🛠️ Key Profiling & Assessment Steps

### 1️⃣ Column Quality & Completeness
- Enabled Power Query's built-in **Column Quality** metrics to evaluate data validity.
- Audited each column for:
  - **Valid %**: Percentage of correctly parsed and typed records.
  - **Error %**: Percentage of corrupted data or conversion failures.
  - **Empty %**: Percentage of null or missing values.

![Column Quality and Health Check](./images/YOUR_COLUMN_QUALITY_IMAGE_NAME.jpg)
*Figure 2.1: Column Quality view displaying valid, error, and empty percentages across dataset fields.*

---

### 2️⃣ Column Value Distribution & Uniqueness
- Activated **Column Distribution** tools to inspect value patterns and uniqueness.
- Assessed cardinality across key dimensions:
  - **Distinct Values**: Total count of unique elements per column.
  - **Unique Values**: Values that appear exactly once in the column.
- Identified potential duplicate records and unexpected text variations.

![Column Value Distribution](./images/YOUR_COLUMN_DISTRIBUTION_IMAGE_NAME.jpg)
*Figure 2.2: Column Distribution histogram showing unique vs. distinct count profiles.*

---

### 3️⃣ Descriptive Statistics & Data Profiling
- Leveraged the **Column Profile** pane for deep statistical analysis on numeric and date fields.
- Analyzed descriptive statistics including:
  - **Minimum & Maximum** boundary values.
  - **Average / Mean** measure distributions.
  - **Null & Zero Count** counts for business logic validation.
- Validated that historical date ranges and numeric ranges align with reporting requirements.

![Column Profile Statistics](./images/YOUR_COLUMN_PROFILE_IMAGE_NAME.jpg)
*Figure 2.3: Detailed summary statistics and descriptive profile for individual dataset fields.*

---

## 📈 Outcomes & Summary Findings

- **Data Integrity Verified**: Confirmed zero critical errors across key date, sales representative, and region attributes.
- **Anomalies Highlighted**: Flagged missing entries and extreme values for handling during downstream custom transformations.
- **Model Readiness**: Ensured columns are prepared for schema alignment, custom M function processing, and DAX metric calculation.

---

## 🔗 Related Links & Steps

* ⬅️ **Previous Step:** [1️⃣ Connect Data & Reformat Columns](./ConnectData_Reformat_Headers_columns-1.md)
* ➡️ **Next Step:** [3️⃣ Custom Functions (Advanced Query Editor)](./query_advanced_editor_customFun-3.md)
* 🏠 **Main Repository:** [Power BI Analysis Repo](https://github.com/yourexodus/mfrancis_PowerBI_Analysis)
* 🌐 **Portfolio Site:** [Marlainna The Analyst Portfolio](https://yourexodus.github.io/MarlainnaTheAnalyst/)
