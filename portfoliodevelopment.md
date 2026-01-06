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

**Purpose:** Demonstrates axis assignment, measure layering, and formatting for clear trend analysis.  

---

### 2️⃣ Suggested Visual: Sales by Product and Category
- **Y-Axis:** Product  
- **X-Axis:** Sum of Sales  
- **Legend:** Category  

![Sales by Product and Category](images_DAX/sales_by_product_category.jpg)  
📁 Images: `images_DAX/`  

**Purpose:** Shows Power BI’s **Suggested visual** feature, highlighting top-performing products and category distribution.  

---

## 🖼 Visual Construction Process
Steps to build and enhance visuals:

1. **Stacked Bar Chart Construction**  
![Click stacked bar chart](images_DAX/ClickStackedBarChart.jpg)  
![Build stacked bar chart](images_DAX/BuildStackedBarchart.jpg)  

2. **Add Measures to Create Combo Chart**  
![Sales Profit Cost graph build](images_DAX/SalesProfitCostGraphBuild.jpg)  

3. **Final Dashboard Output**  
![Post dashboard](images_DAX/PostDashboard.jpg)  

---

## 🧮 DAX & Measures Notes
- Sales and Profit aggregated using **implicit measures** (Sum)  
- Measure placement affects visual behavior (X/Y-axis roles)  
- Formatting options vary by visual type and UI version  

> Highlights the importance of understanding **semantic model behavior**, even without custom DAX.

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
6. Publish and interpret results  

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

---

✅ **Notes:**  
Organized images and screenshots follow real-world analytics documentation conventions:  

- `images_charting/` → Combo charts & formatting  
- `images_DAX/` → Suggested visuals & field exploration  