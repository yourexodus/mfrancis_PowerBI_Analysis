## 📊 Dashboard Overview

This Power BI dashboard provides insights into:

* **Sales performance** by region
* Breakdown by **sales representative**
* **Monthly sales trends**
* Data quality improvements through **Power Query**
* Year-to-date summaries

The dataset originally contained missing values, no headers, unstructured date columns, and combined fields—requiring multiple stages of cleanup.

---

## 🧹 Data Cleaning & Transformation (Power Query)

Below is the exact transformation pipeline used in Power Query.

### 1. Removed Null Rows

Deleted the first two rows containing null values.
Used: **Home → Reduce Rows → Remove Top Rows**.

### 2. Promoted First Row to Headers

Enabled meaningful column names.
Used: **Home → Use First Row as Headers**.

![Promoted Headers with Date and Sales Rep columns](myimages/AfterSelectedUseFirstRowAsHeaders.jpg)

### 3. Split “Sales Rep” Into Region + Rep Name

The Sales Rep field originally contained data in the format: **Region - Name**.
The column was split by the delimiter **(-) and the resulting fields were renamed**:

* Sales Rep.1 $\rightarrow$ **Region**
* Sales Rep.2 $\rightarrow$ **Sales Rep Name**

![Data after splitting Sales Rep and renaming columns Region and Sales Rep Name](myimages/DataAfterRename.jpg)
![Applied Steps pane showing the Split Column by Delimiter and Renamed Columns steps](myimages/AppliedStepsAfterColumnRename.jpg)

### 4. Unpivoted Monthly Date Columns

Converted wide-format date columns (e.g., 1/31/2023, 2/28/2023, etc.) into a long-format table, transforming the columns as follows:

* `Attribute` $\rightarrow$ **Date**
* `Value` $\rightarrow$ **Number of Sales**

![Applied Steps pane showing the Unpivoted Columns step](myimages/AppliedStepsAfterunpivot.jpg)
![Data table showing Date Region Sales Rep Name and Number of Sales columns after unpivoting](myimages/AfterReformateOfDateColumn.jpg)

### 5. Data Type Formatting

* Converted the **Number of Sales** column $\rightarrow$ **Whole Number**.
    * *Note: Original column type was text/ABC 123.*
    ![Number of Sales column before changing the data type from Text/ABC to Whole Number/123](myimages/beforeNumberOfSalesDataTypeChange.jpg)
    ![Number of Sales column after changing the data type to Whole Number](myimages/AfterDataTypeChange.jpg)
* Converted the **Date** column $\rightarrow$ **Date type**.
* **Reordered** the **Date** column to be the first column.

### 6. Final Review & Apply

* Reviewed the **“Changed Type”** steps.
* **Removed incorrect type conversions** (as shown in the Applied Steps pane).
    * *Before Deletion:* The applied steps had a redundant `Renamed Columns1` step followed by `Changed Type1`, `Reordered Columns`, and `Changed Type2`.
    ![Applied Steps pane showing multiple redundant steps before cleanup](myimages/BeforeDeleteChangeSteps.jpg)
* **Applied** all transformations using **Close & Apply**.
![Power Query Home tab menu showing the Close & Apply option highlighted](myimages/ClickHomeCloseApply.jpg)

![Final table structure after all transformations including Date Region Sales Rep Name and Number of Sales](myimages/AfterCorrection.jpg)

---

## 🏗 Data Model

Tables included in the model:

* **Transformed Sales Data** (fact table)
* **Sales Rep Data** (dimension attributes)

### Key Modeling Notes:

* Clean **star-schema** ready structure.
* Proper **date formatting** to support time-series visuals.
* All fields labeled and cleaned to support reporting.

---

## 📈 Dashboard Features

* Monthly sales trend line
* Sales by region bar chart
* Sales by representative
* KPI card summarizing overall sales
* Filter interactions and slicers for dynamic exploration

---

## 🛠 Tools Used

| Tool | Purpose |
| :--- | :--- |
| Power BI Desktop | Dashboard creation & modeling |
| Power Query | Data cleaning & shaping |
| Excel | Data source |
| DAX | Metrics & calculations |
| Power BI Service | Web publishing |