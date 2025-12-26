# Government Employment Analysis (Power BI)

## Overview
This project documents a **step-by-step Power BI analysis** of U.S. government employment data from the Bureau of Labor Statistics (BLS).

The purpose of this project is to:
- Practice **real-world data acquisition**
- Perform **data shaping and transformation**
- Correct common **time-series visualization issues**
- Interpret employment changes responsibly

This is a **process-focused analysis**, not just a final chart.

---

## Data Source
- **Source:** U.S. Bureau of Labor Statistics (BLS)
- **Access Method:** Power BI Web Connector
- **Frequency:** Monthly
- **Scope:** U.S. Government employment data

---

## Step 1: Connect to the Data Source

![Get Data from Web](images_laborStatistics/Getdata_web.jpg)

Power BI’s **Web connector** was used to access employment data directly from the BLS website.

![Paste Website](images_laborStatistics/PasteWebSite.jpg)

The source URL was pasted and previewed to verify the correct table before loading.

![Accept Connections](images_laborStatistics/AcceptConnections.jpg)

Connections were accepted to allow Power BI to retrieve the dataset.

---

## Step 2: Review the Raw Data

![Preview Data](images_laborStatistics/ReviewSomeData.jpg)

Initial inspection revealed:
- Multiple header rows
- Extra metadata
- Wide-format monthly columns

![Observe US Employment Data](images_laborStatistics/ObserveUSemploymentdata.jpg)

Only the U.S. employment table was relevant for this analysis.

---

## Step 3: Open Power Query for Transformation

![Transform Data](images_laborStatistics/ClickTransformData.jpg)

Power Query was used to clean and reshape the dataset.

![Use First Row as Headers](images_laborStatistics/UseFirstRowHeaders.jpg)

The first row was promoted to headers for proper field naming.

---

## Step 4: Remove Unnecessary Data

![Select Columns](images_laborStatistics/SelectColumns.jpg)

Only relevant columns were retained.

![Delete Value Column](images_laborStatistics/DeleteTheValueColumn.jpg)

Unneeded value columns were removed to simplify the dataset.

---

## Step 5: Reshape the Data (Unpivot)

![Unpivot Columns](images_laborStatistics/UnpivotColumns.jpg)

Monthly columns were unpivoted to convert the data into a **long format** suitable for time-series analysis.

![Completed Transpose](images_laborStatistics/completedTranspose.jpg)

The resulting structure created:
- One column for Month
- One column for Employment values

---

## Step 6: Clean and Rename Fields

![Rename Table](images_laborStatistics/RenameTable.jpg)

Tables were renamed for clarity.

![Rename Category Month](images_laborStatistics/RenameCategoryMonth.jpg)

Month categories were renamed to improve readability.

![Change Category to Month](images_laborStatistics/ChangeCategorytoMonth.jpg)

Month fields were explicitly assigned as date-related values.

---

## Step 7: Fix Date & Sorting Issues

![Date Column](images_laborStatistics/DateColumn.jpg)

A proper Date column was created.

![Use Month Date X Axis](images_laborStatistics/UseMonthDateXaxis.jpg)

The X-axis was updated to use a true date field instead of text.

![Sept 2025 Remove Blanks](images_laborStatistics/Sept2025RemoveBlanks.jpg)

Blank or incomplete month values were removed to prevent chart distortion.

> Correct time-series sorting is critical. Incorrect month order can mislead viewers even when data is accurate.

---

## Step 8: Build the Visualization

![Build a Chart](images_laborStatistics/BuildAChart.jpg)

A **line chart** was selected to show employment trends over time.

![Select Line Chart](images_laborStatistics/SelectLineChart.jpg)

Government employment was added to the Values field.

![Sum of Government](images_laborStatistics/SumOfGovernment.jpg)

Aggregation was verified to ensure values were summed correctly.

---

## Step 9: Format for Clarity and Focus

![Format Pane](images_laborStatistics/CickFormatPane.jpg)

Formatting options were accessed to refine the visual.

![Select Government as Bold Red](images_laborStatistics/SelectGovernmentAsBoldRed.jpg)

Government employment was emphasized using bold red formatting.

![Government Red](images_laborStatistics/GovernmentRed.jpg)

Other series were visually de-emphasized.

![Dashed Government Line](images_laborStatistics/FormatPaneDashedGovernment.jpg)

Line styles were adjusted to guide attention.

---

## Step 10: Labels, Titles, and Readability

![Turn Off Data Labels](images_laborStatistics/TurnDatalabelsOFF.jpg)

Data labels were turned off globally.

![Show Labels for Government Only](images_laborStatistics/ShowForSeriesLabelGovernment.jpg)

Labels were selectively enabled for the focus series.

![Title Update](images_laborStatistics/TitleUpdate.jpg)
![After Title and Text](images_laborStatistics/AftertitleandText.jpg)

Titles and explanatory text were added to improve interpretation.

---

## Step 11: Final Result & Key Observation
![November Rebound](images_laborStatistics/NovemberRebound.jpg)


The final visualization shows:
- A **decline from September to October**
- A **rebound in November**


![Final Graph](images_laborStatistics/FinalGraph.jpg)

### Interpretation
This decline does **not automatically indicate layoffs**.  
Possible explanations include:
- End-of-fiscal-year adjustments
- Temporary hiring pauses
- Budget or funding cycle timing

Context is essential when interpreting employment data.

---

## Skills Demonstrated
- Power BI Web data ingestion
- Power Query transformations
- Time-series correction
- Visual storytelling
- Responsible labor market interpretation

---

## Portfolio Context
This project reflects my ability to:
- Document analytical workflows clearly
- Preserve data integrity
- Communicate insights professionally
- Explain complex trends without exaggeration

---

## Repository
`mfrancis_PowerBI_Analysis`
