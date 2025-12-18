
## Purpose of This Work

The goal of this data shaping process was to:

- Prepare sales data for accurate reporting
- Validate and manage relationships between tables
- Clean and format data to prevent reporting errors
- Create calculated columns to support analysis
- Build report visuals from a properly modeled dataset

---

## Reviewing and Managing Table Relationships

The first step was to review all existing relationships in the data model to ensure they were correct and active.

- Opened **Model View** to inspect table connections
- Verified **cardinality** between tables (many-to-one where expected)
- Ensured correct primary and foreign keys were being used
- Identified inactive or missing relationships

![Relationships](images_dataShaping/Relationships.jpg)
![Cardinality](images_dataShaping/cardinality.jpg)
![Manage Relationships](images_dataShaping/managerelationships.jpg)

---

## Activating and Correcting Relationships

Some relationships required activation or adjustment to ensure filters flowed correctly across tables.

- Selected inactive relationships
- Confirmed join columns
- Set relationships to **Active**
- Saved updates to the model

![Make Relationship Active](images_dataShaping/MakeRelationshipActive.jpg)

---

## Date Table Relationship Validation

A key step was validating the relationship between the **Date table** and the **Sales Orders table**.

- Confirmed the correct date column was used
- Ensured relationship direction supported reporting needs
- Saved relationship changes once verified

![Check the Date](images_dataShaping/checktheDate.jpg)
![Date Relationship Completed](images_dataShaping/DateRelationshipCompleted.jpg)
![Date to Sales Order Relationship Save](images_dataShaping/DateToSalesOrderRelationshipSave.jpg)

---

## Appending Sales Tables

Historical sales data was combined into a single table using Power Query.

Steps included:
- Selecting **Append Queries**
- Appending multiple sales tables together
- Verifying column alignment
- Applying changes to load data into the model

![Click Append Queries](images_dataShaping/ClickAppendQueries.jpg)
![Append Two Tables](images_dataShaping/AppendtwoTables.jpg)
![Close and Apply](images_dataShaping/CloseApply.jpg)

---

## Cleaning and Validating Data

Data cleanup was required to remove invalid or incomplete records.

Actions taken:
- Identified rows with missing Customer IDs
- Removed rows containing errors
- Used filters to exclude invalid data
- Ensured only clean records remained in the dataset

![Missing Customer ID](images_dataShaping/MissingCustomerID.jpg)
![Remove Errors Using Filter](images_dataShaping/removeErrorsUsingFilter.jpg)

---

## Data Formatting and Categorization

To ensure correct aggregation and reporting behavior, several formatting updates were applied.

### Formatting Steps
- Set correct **data categories** (city, state, postal code)
- Applied **currency formatting** to monetary fields
- Disabled summarization for numeric fields used as attributes
- Standardized date formats

![Data Category](images_dataShaping/DataCategory.jpg)
![Currency Format](images_dataShaping/CurrencyFormat.jpg)
![Dont Summarize](images_dataShaping/DontSummarize.jpg)
![Format Date](images_dataShaping/formatDate.jpg)

---

## Creating a Calculated Column: Days to Ship

A calculated column was added to measure shipping performance.

Steps included:
- Creating a new column in Power Query
- Calculating the difference between Order Date and Ship Date
- Converting the result to a whole number
- Validating values for accuracy

![Insert Days to Ship](images_dataShaping/DoubleClickOrInsertDaystoShip.jpg)
![Days to Ship Whole Number](images_dataShaping/DaysToShipWholeNumber.jpg)
![Review Order Date Ship Date](images_dataShaping/ReviewOrderDateShipDate.jpg)

---

## Report View and Visual Creation

After data preparation, the focus shifted to building visuals in Report View.

Steps performed:
- Returned to Report View
- Selected appropriate visuals
- Added fields from cleaned tables
- Verified that filters and relationships worked as expected

![Click Model View](images_dataShaping/clickModelView.jpg)
![Click Focus Mode](images_dataShaping/ClickFocusMode.jpg)
![Select Table Visual](images_dataShaping/SelectTableVisual.jpg)
![Table Visual Result](images_dataShaping/TableVisualResult.jpg)

---

## Final Report Review

The final report includes sales, profit, and shipping-related metrics derived from the cleaned and modeled data.

- Verified visuals updated correctly after transformations
- Confirmed calculated columns displayed accurate values
- Ensured report was ready for analysis

![New Visual](images_dataShaping/Report_NewVisual.jpg)
![Sales Profit Shipping](images_dataShaping/SalesProfitShipping.jpg)
![Back to Report](images_dataShaping/BacktoReport.jpg)
![Back to Report After Adding Date Ship](images_dataShaping/BacktoReportafterAddingdateship.jpg)

---

## Skills Demonstrated

- Power BI Data Modeling
- Relationship Management
- Power Query Transformations
- Data Cleaning & Validation
- Calculated Columns
- Report Development

---

## Tools Used

- Power BI Desktop
- Power Query Editor

---

## Notes

This documentation reflects the **exact steps and workflow** captured in the original project notes and screenshots.  
No assumptions or undocumented steps were added.