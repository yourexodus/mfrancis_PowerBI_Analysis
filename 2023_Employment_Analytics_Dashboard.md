# 📊 Sales Analytics Dashboard (Power BI)

> **An end-to-end Power BI project demonstrating data modeling, DAX problem-solving, and executive-ready data storytelling.**

---

## 🔍 Project Overview
This project analyzes sales performance using Microsoft Power BI, with a focus on exploring sales trends across time, products, categories, subcategories, and regions.

The project documents the development process from data import and exploration through visualization, data modeling, troubleshooting, and final dashboard refinement.

Rather than showing only the finished report, the project captures the iterative process used to build and improve the dashboard.
---

## 🎯 Business Question
The dashboard was developed to explore:

How sales change over time
How sales vary across regions
Which product categories and subcategories are represented in the sales data
How different visualizations can be used to analyze sales performance
How sales information can be presented in an interactive business dashboar
---

## 🛠 Tools & Technologies
- Power BI Desktop  
- DAX (Calculated Columns)  
- Power Query (Data Cleaning)  
- Time-Series Analysis  
- Business Intelligence & Data Storytelling  

---

## 📁 Data Preparation & Modeling

### Problem: Month Sorting Error
Month values were stored as text (e.g., `June 2023 (p)`), which caused **alphabetical sorting** in visuals.

❌ June → July → May  
✅ May → June → July  

### Solution: DAX Helper Column
A calculated date column was created to enforce chronological sorting.

```DAX
MonthDATE = 
VAR CleanText = 
    TRIM(
        SUBSTITUTE('establishement_data'[Month], "(p)", "")
    )
VAR YearNum = 
    VALUE(RIGHT(CleanText, 4))
VAR MonthNum = 
    MONTH(
        DATEVALUE(
            LEFT(CleanText, 3) & " 01 2000"
        )
    )
RETURN
DATE(YearNum, MonthNum, 1)
```

The helper column was used with **Sort by Column** and then hidden for a clean data model.

---

## 🧱 Visual Development Process

### Data Import & Exploration
![Imported Data](images_visuals/ImportedData.jpg)
![Extract Data](images_visuals/extractData.jpg)
![Extract From Other PBIX](images_visuals/ExtractDatafromOtherPOWERBI.jpg)

---

### Initial Visual Builds
![Blank Bar Chart](images_visuals/BlankBarChart.jpg)
![Stacked Bar](images_visuals/stackedBar.jpg)
![Stacked Bar Chart](images_visuals/stackedBarChart.jpg)
![Compare Graphs](images_visuals/compareGraphs.jpg)

---

### Sorting & Modeling Fix
![Sort Graph Issue](images_visuals/Sortgraph.jpg)
![Added DAX](images_visuals/AddedDaxToEstTable.jpg)
![Turn On Arrange Date](images_visuals/TurnOnArrangedateforME.jpg)
![After Sort by Month](images_visuals/AfterSortbyMonth.jpg)

---

### Visual Refinement
![Suggest Visual](images_visuals/SuggestAVisual.jpg)
![Suggest Line Chart](images_visuals/SuggestLineChart.jpg)
![Compare Stacked Bar](images_visuals/CompareStackedBar.jpg)
![Drag Region to Legend](images_visuals/DragRegionToLegend.jpg)
![Move Data to Canvas](images_visuals/moveEstaDataToCanvas.jpg)
![Move Category Canvas](images_visuals/MoveProductCateogrySubCatgoryCanvas.jpg)

---
 

### Final Visuals & Polish
![Updated Title](images_visuals/UpdateTitle.jpg)
![Updated Sales by Date](images_visuals/UpdatedSalesByOrderDate.jpg)
![Card Visual](images_visuals/Card_SalesData.jpg)
![Final Clustered Graph](images_visuals/finalClusteredGraph.jpg)

---
 

## 💡 Key Insights
- Government employment showed **isolated volatility**, diverging from all other sectors  
- **June 2023** accounted for over **50% of total quarterly growth**  
- Other sectors remained comparatively stable, confirming the outlier behavior  

---

## 💼 Business Value
This dashboard enables stakeholders to:
- Detect abnormal employment trends quickly  
- Understand cumulative vs. point-in-time changes  
- Rely on clean, chronologically accurate reporting  

---

## 🧠 Why This Project Is Portfolio-Ready
✔ Demonstrates real-world **DAX problem-solving**  
✔ Shows full **analysis lifecycle**, not just visuals  
✔ Applies **executive-level storytelling**  
✔ Uses best practices in Power BI modeling and design  

---

*Created by Marlainna Francis — Power BI | Data Analytics | Business Intelligence*
