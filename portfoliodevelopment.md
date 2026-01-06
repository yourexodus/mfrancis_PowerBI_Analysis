# Power BI Visualization & DAX Exploration Project

## 📊 Project Overview
This project demonstrates hands-on **Power BI** skills through interactive visual creation, formatting, and exploratory analysis of **Sales and Profit data**. Key components include combo charts, suggested visuals, category-based comparisons, and a focus on Power BI’s modern interface and analytical workflow.  

All visuals and documentation are hosted via **GitHub images** and a **published Google Doc** to make the project recruiter-accessible.

---

## 🎯 Objectives
- Build and format Power BI visuals using best practices  
- Explore **Suggested visuals** and understand data-role mapping  
- Compare Sales performance by Product and Category  
- Apply formatting for clarity and business-readiness  
- Publish a structured analytics walkthrough for portfolio presentation  

---

## 🛠 Tools & Technologies
- **Power BI Desktop**  
- **DAX** (implicit measures & aggregations)  
- **GitHub** (image hosting/documentation)  
- **Google Docs** (published report)  

---

## 🧱 Data Model Setup & Field Confirmation
Before creating visuals, we validated key tables and fields to ensure proper context and accurate calculations.

### 🔹 View Products Table
![View Products table](images_DAX/ViewProducttableView.jpg)  
Shows Product ID, Product Name, Category, SubCategory, and pricing-related fields.

### 🔹 Select Key Product Fields
![Select Product ID](images_DAX/SelectProdID.jpg)  
![Select Product Name](images_DAX/SelectProductName.jpg)  

**Selected fields:**  
- **Product ID** → primary key  
- **Product Name** → labels  

These steps ensure accurate field mapping before downstream calculations.

### 🔹 Observe New Calculated Fields
![Observe new field](images_DAX/ObserveNewField.jpg)  
![Observer view new field](images_DAX/Observerview new field.jpg)  

Calculated fields are created and ready for use in visuals.

---

## 🧮 Calculated Fields & Cost Logic
### 🔹 Cost Calculation
![Cost column](images_DAX/Costcolumn.jpg)  
![Cost formula](images_DAX/CostFormula.jpg)  
![Formula bar](images_DAX/FormulaBar.jpg)  

This ensures the **Cost** measure is accurate for combo chart analysis.

---

## 🎨 Formatting & Money Fields
### 🔹 Apply Currency Formatting
![Select currency](images_DAX/SelectCurrency.jpg)  
![Currency formatting](images_DAX/Currency.jpg)  
![Format cost](images_DAX/FormatCost.jpg)  

Formatted measures improve readability and business interpretation.

---

## 📊 Visualizations

### 1️⃣ Combo Chart: Sales vs Profit
- **X-Axis:** SubCategory  
- **Column Y-Axis:** Sum of Sales  
- **Line Y-Axis:** Sum of Profit  
- **Legend:** Region  
- **Visual Type:** Line and Clustered Column Chart  

📁 Images: `images_charting/`  

**Purpose:** Demonstrates axis assignment, measure layering, formatting, and interactive sorting for clear trend analysis.  

**Step-by-Step Visual Build:**

1. **Add Profit Measure to Value**
![Add Profit to Value](images_charting/AddProfittoValue.jpg)

2. **Create & Build Scatter Chart**
![Build Scatter Chart](images_charting/BuildScatterChart.jpg)  
![Create Scatter Chart](images_charting/CreateScatterChart.jpg)

3. **Adjust Bubble Size & Final Graph**
![Increase Bubble Size](images_charting/Increasebubblesize.jpg)  
![Final Graph Scatter Chart](images_charting/FinalGraphScatterChart.jpg)

4. **Apply Tooltip Interactivity**
![Create Tooltip](images_charting/CreateTooltip.jpg)  
![Current Sales & Profit Tooltip](images_charting/CurrentSalesProfitToolTip.jpg)  
![Update Tooltips](images_charting/UpdateTooltips.jpg)  
![Tooltip Applied](images_charting/TooltipApplied.jpg)

5. **Sort Categories & Profit**
![Sort Category Ascending](images_charting/SortCategoryAscending.jpg)  
![Sort Region Ascending](images_charting/SortRegionAscendintg.jpg)  
![Sort by Sum of Profit](images_charting/SortBySumOfProfit.jpg)  
![After Category Sorted](images_charting/AfterCategorySorted.jpg)  
![After Profit Sort](images_charting/AfterProfitSort.jpg)

---

### 2️⃣ Map Visuals & Geospatial Insights
- **Enable Map Feature**  
![Turn On Map Feature](images_charting/TurnOnMapFeature.jpg)  
![Enable Map Click Apply](images_charting/EnableMapClickApply.jpg)  
![Click Create Map](images_charting/ClickCreateMap.jpg)  
- **Add Borders & Final Formatting**  
![Turn On Border](images_charting/TurnOnBorder.jpg) | ![View Borders](images_charting/ViewBorders.jpg)  
- **Final Maps**
![Final Map with Tooltip](images_charting/FinalMapwithTooltip.jpg)  
![Final Map by Category and Region](images_charting/finalMapByCategoryAndREgion.jpg)  
- **Error Handling**  
![Map Error](images_charting/MapError.jpg)

---

### 3️⃣ Line & Stacked Column Charts
- **Line and Clustered Column Construction**
![Home Line Stacked Column Chart](images_charting/HomeLineStackedColumnChart.jpg)  
![Line Stacked Chart Data 3 Tables](images_charting/LIneStackedChartData3Tables.jpg)  
![Finished Line Stacked Column Chart](images_charting/FinishedLineStackedColumnChart.jpg)  
![Completed Stacked Column Chart](images_charting/CompletedStackedColumnChart.jpg)

---

### 4️⃣ Gauge & Target Visuals
![Click Gauge](images_charting/ClickGauge.jpg)  
![Finished Gauge Visual](images_charting/FinishedGaugeVisual.jpg)  
![Enter Target 120000](images_charting/EnterTarget120000.jpg)

---

### 5️⃣ Infographics & AppSource Visuals
![AppSource Visuals](images_charting/AppSourceVisuals.jpg)  
![New Infographic Visual](images_charting/NewInfographicVisual.jpg)  
![Search Infographic Designer](images_charting/SearchInfoGraphicDesigner.jpg)  
![Click Infographic Designer](images_charting/clickInfographicDesigner.jpg)  
![Info Designer So Far](images_charting/infoDesignerSoFar1.jpg)  

---

### 6️⃣ Customization & Final Touches
- **Color Palettes & Contrast**
![Select Color Blind Safe Palette](images_charting/SelectColorBlindSafe.jpg)  
![Expand Colors](images_charting/expandcolors.jpg)  
![More Contrast](images_charting/morecontrast.jpg)

- **Resize, Update Titles & Integration**
![Resize Completed Visuals](images_charting/resizeCompleted.jpg)  
![Select Light Blue](images_charting/selectLightBlue.jpg)  
![Update Title](images_charting/updateTitle.jpg)  
![Integration Settings](images_charting/Integrationsettings.jpg)

---

### 7️⃣ Final Dashboard Outputs
- **Total by Region, Category, SubCategory**
![Total by Region, Category, SubCategory](images_charting/TotalbyRegionCatSubCat.jpg)  
- **Final Shipping Cost by Category & Region**
![Final Shipping Cost](images_charting/FinalShippingcostforEachCategorybyRegion.jpg)  
- **Interactions**
![After Clicking Boat](images_charting/afterclickBoat.jpg)  
![Click Shape](images_charting/clickShape.jpg)  
![Click Transportation Boat](images_charting/clickTransportationBoat.jpg)  

---

## 📄 Published Report
Full walkthrough with explanations and visuals:  

🔗 [Published Google Doc](https://docs.google.com/document/d/e/2PACX-1vRzCm8RpqCNMi6-PjiWiCsDbZQoLWPQd12uR3bcsrMBDfZAxsFJlrqXaGvW04YVC93QRo-EEKDnlW68/pub)  

**Process Overview:**  
1. Validate tables and key fields  
2. Create calculated fields  
3. Format measures  
4. Build base visuals (Sales & Profit combo)  
5. Refine titles, sort orders, and formatting  
6. Add map & tooltip interactivity  
7. Integrate gauges, line/stacked columns, and infographics  
8. Publish and interpret results  

---

## 💡 Key Takeaways
- Visual field placement directly impacts formatting options  
- Power BI’s **Suggested visuals** accelerate exploratory analysis  
- UI updates require adaptability when following older guides  
- Structured documentation enhances portfolio credibility  

---

## 📬 Author
**Marlainna Francis**  
Data Analyst | Business Intelligence | Analytics  

🌐 Portfolio: [yourexodus.github.io/MarlainnaTheAnalyst](https://yourexodus.github.io/MarlainnaTheAnalyst/)  
🐙 GitHub: [github.com/yourexodus](https://github.com/yourexodus)  