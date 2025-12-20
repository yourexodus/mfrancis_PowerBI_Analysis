# Power BI Data Shaping & Modeling

This document walks through the **data shaping and modeling work** done in Power BI Desktop for the Sales dataset.  
All steps and screenshots reflect the documented workflow from the original project notes. :contentReference[oaicite:2]{index=2}

> **Note:** Images are stored in the repository at:
>
> `images_dataShaping/`

---

## Purpose

This project focused on preparing the dataset for accurate reporting and analysis by:

- Reviewing and activating relationships between tables  
- Appending multiple sales tables  
- Cleaning and transforming data  
- Setting correct data categories, including geographic fields  
- Creating calculated columns  
- Building visuals and confirming data integrity in the report view

---

## 🧩 Reviewing and Activating Relationships

### Review Relationships  
Opened the Model view to inspect table relationships and cardinality.

![Click Model View](images_dataShaping/clickModelView.jpg)
![Relationships](images_dataShaping/Relationships.jpg)
![Cardinality](images_dataShaping/cardinality.jpg)

### Manage and Activate Relationships  
Activated any inactive relationships to ensure proper filtering across tables.

![Manage Relationships](images_dataShaping/managerelationships.jpg)
![Make Relationship Active](images_dataShaping/MakeRelationshipActive.jpg)

---
## 📅 Date Table Relationship

Connected the **Date** table to the **Sales Orders** table by dragging the Date field to Order Date.

![Date Relationship Completed](images_dataShaping/DateRelationshipCompleted.jpg)
![Date to Sales Order Relationship Save](images_dataShaping/DateToSalesOrderRelationshipSave.jpg)

---

## 📌 Summarization Settings

Disabled summarization for the `MonthNum` field in the Date table.

> This avoids Power BI automatically summing month numbers in visuals. :contentReference[oaicite:3]{index=3}

*(If you have a screenshot of this, add it here)*

---

## ➕ Appending Sales Tables

Appended the historical Sales Orders (2019–20) table into the main Sales Orders table.


Steps:

1. Select Home→Transform data→Transform data.
2. In the Queries pane, select the Sales Orders table.
3. Select Home→Append Queries→Append Queries.

![Click Append Queries](images_dataShaping/ClickAppendQueries.jpg)

Steps:

1. Home→Combine→Append Queries→Append Queries.
2. In the Append dialog box, verify that Two tables is selected.
3. From the Table to append drop-down menu, select Sales Orders2019-20.



![Append Two Tables](images_dataShaping/AppendtwoTables.jpg)

Click Ok, close and Apply

![Close and Apply](images_dataShaping/CloseApply.jpg)

---

## 📊 Create Table Visual (Basic Confirmation)

Returned to Report View and added a Table visual to confirm that data loaded correctly.

![Report view](images_dataShaping/clickREportView.jpg)

Home→ Table Icon.
Confirm the Table visualization is selected

![ClickFocusMode](images_dataShaping/ClickFocusMode.jpg)
YOU will see the New Visual Option after you click the Report View


![TableVisualResult](images_dataShaping/TableVisualResult.jpg)

Expand the Data pane on the right
Drag or check the following fields 
Tables
Customers: Customer Name
Products:Product Name
Date: Year, Month

![BacktoREport](images_dataShaping/BacktoREport.jpg)

Click Back to Report


---

## 🧹 Cleaning and Removing Errors

Identified and removed records with erroneous Customer IDs from the Sales Orders table.

Remove Errors using Filter


![Missing Customer ID](images_dataShaping/MissingCustomerID.jpg)

Steps:
1. Select Home→Transform data→Transform data.
2. In the Queries pane, select the Sales Orders table.
3. In the center pane, in the Customer ID header, expand the drop-down list.
4. You might have to scroll to the right to see the Customer ID column.
5. Scroll down and uncheck the W-171251 check box.
6. Cick ok
7. Click close and apply

![Remove Errors Using Filter](images_dataShaping/removeErrorsUsingFilter.jpg)

---


## 🔢 Data Formatting

Applied currency and number formatting so fields like Sales, Profit, and Shipping Cost display correctly.

![Currency Format](images_dataShaping/CurrencyFormat.jpg)
![Dont Summarize](images_dataShaping/DontSummarize.jpg)
![Format Date](images_dataShaping/formatDate.jpg)

---

## 📍 Setting Geographic Data Types

Assigned the correct data category for geographic fields in the Customers table:

1. Expanded **Customers** in the Data pane. :contentReference[oaicite:4]{index=4}  
2. Set **City** → *City*  
3. Set **Country** → *Country*  
4. Set **State** → *State or Province*  
5. Set **Zip Code** → *Postal code*  
6. Returned to Report View and saved.

![Data Category](images_dataShaping/DataCategory.jpg)

> Assigning correct geographic categories enables accurate mapping and filtering.

---

## 📐 Calculated Column: Days to Ship

Created a **Days to Ship** column to measure shipment duration:

- Used the Add Column → Custom Column feature
- Subtracted Order Date from Ship Date
- Converted output to Whole Number

![Insert Days to Ship](images_dataShaping/DoubleClickOrInsertDaystoShip.jpg)
![Days to Ship Whole Number](images_dataShaping/DaysToShipWholeNumber.jpg)
![Review Order Date Ship Date](images_dataShaping/ReviewOrderDateShipDate.jpg)

---

## 📈 Review in Report View

Confirmed that visuals are working with cleaned and transformed data:

- Checked table visuals  
- Added fields from Customers, Products, and Date tables


![Click Focus Mode](images_dataShaping/ClickFocusMode.jpg)
![Select Table Visual](images_dataShaping/SelectTableVisual.jpg)
![Table Visual Result](images_dataShaping/TableVisualResult.jpg)

---

## 📊 Final Report Review

Verified visuals after all transformations were applied:

![New Visual](images_dataShaping/Report_NewVisual.jpg)
![Sales Profit Shipping](images_dataShaping/SalesProfitShipping.jpg)
![Back to Report](images_dataShaping/BacktoReport.jpg)
![Back to Report After Adding Date Ship](images_dataShaping/BacktoReportafterAddingdateship.jpg)

---

## 🛠 Skills Demonstrated

- Power BI Data Modeling  
- Query Transformation & Cleaning  
- Geographic Data Categorization  
- Calculated Columns  
- Visual Validation  
- Report View Verification

---

## 🧰 Tools Used

- Power BI Desktop  
- Power Query Editor  
- Built-in Power BI modeling features