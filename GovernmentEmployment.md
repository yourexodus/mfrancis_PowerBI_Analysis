# Government Employment Analysis (Power BI)

## Overview
This project analyzes **U.S. government employment trends** using data from the Bureau of Labor Statistics (BLS). The focus is on **data preparation, time-series accuracy, and clear analytical storytelling** using Power BI.

This is not an interactive dashboard.  
Instead, it documents the **step-by-step analytical process** used to build a correct and trustworthy visualization.

---

## Data Source
- **Source:** U.S. Bureau of Labor Statistics (BLS)
- **Method:** Web data connector in Power BI
- **Frequency:** Monthly employment data
- **Scope:** U.S. Government employment

---

## Step 1: Data Acquisition

![Get Data from Web](images_laborStatistics/Getdata_web.jpg)

Data was retrieved directly from the BLS website using Power BI’s **Web connector**.

![Paste Website](images_laborStatistics/PasteWebSite.jpg)

After pasting the source URL, the data preview was reviewed before loading.

---

## Step 2: Data Review & Initial Cleanup

![Review Data](images_laborStatistics/ReviewSomeData.jpg)

Initial inspection identified:
- Unnecessary columns
- Formatting inconsistencies
- Month values requiring transformation

![Select US Table](images_laborStatistics/SelectUsTableData.jpg)

Only relevant U.S. employment data was retained.

---

## Step 3: Data Transformation (Power Query)

![Transform Data](images_laborStatistics/ClickTransformData.jpg)

Power Query was used to reshape and clean the dataset.

![Use First Row as Headers](images_laborStatistics/UseFirstRowHeaders.jpg)

Headers were promoted to ensure proper field names.

![Unpivot Columns](images_laborStatistics/UnpivotColumns.jpg)

Wide-format data was unpivoted to support time-series analysis.

![Completed Transpose](images_laborStatistics/completedTranspose.jpg)

Data structure was validated after transformation.

---

## Step 4: Date & Category Corrections

![Rename Category Month](images_laborStatistics/RenameCategoryMonth.jpg)

Month values were renamed for clarity.

![Change Category to Month](images_laborStatistics/ChangeCategorytoMonth.jpg)

Month fields were explicitly set for time-based analysis.

![Use Month Date X Axis](images_laborStatistics/UseMonthDateXaxis.jpg)

A proper date field was applied to the X-axis to prevent misordering.

> Correct month sorting is critical. Even correct data can appear misleading if dates are not handled properly.

---

## Step 5: Building the Visualization

![Build a Chart](images_laborStatistics/BuildAChart.jpg)

A line chart was selected to show employment trends over time.

![Select Line Chart](images_laborStatistics/SelectLineChart.jpg)

Government employment was added as the primary value.

![Sum of Government](images_laborStatistics/SumOfGovernment.jpg)

Aggregation was verified to ensure **SUM**, not average.

---

## Step 6: Formatting & Visual Emphasis

![Format Pane](images_laborStatistics/CickFormatPane.jpg)

Formatting controls were used to guide viewer attention.

![Select Government as Bold Red](images_laborStatistics/SelectGovernmentAsBoldRed.jpg)

Government employment was emphasized using color and line weight.

![Dashed Government Line](images_laborStatistics/FormatPaneDashedGovernment.jpg)

Other series were visually muted to reduce noise.

![Turn Off Data Labels](images_laborStatistics/TurnDatalabelsOFF.jpg)
![Show Government Labels Only](images_laborStatistics/ShowForSeriesLabelGovernment.jpg)

Labels were applied selectively to improve readability.

---

## Step 7: Key Observation

![Final Graph](images_laborStatistics/FinalGraph.jpg)

A noticeable decline appears from **September to October**, followed by a **November rebound**.

![November Rebound](images_laborStatistics/NovemberRebound.jpg)

### Interpretation Notes
- This does **not automatically indicate layoffs**
- Possible explanations include:
  - End-of-fiscal-year adjustments
  - Temporary hiring pauses
  - Budget timing effects

Contextual analysis is required before drawing conclusions.

---

## Skills Demonstrated
- Power BI data shaping
- Power Query transformations
- Time-series accuracy
- Visual storytelling
- Responsible labor data interpretation

---

## Portfolio Context
This project demonstrates my ability to:
- Clean and reshape real-world labor data
- Correct common visualization mistakes
- Explain trends without overstatement
- Communicate findings clearly and professionally

---

## Repository
`mfrancis_PowerBI_Analysis`