# 📘 Power BI -- Advanced Editor & Custom Function Guide

## Sales Tier Classification Using M Code and Custom Functions

(Images stored in your **images_advancedEditor** folder.)

---

## #️⃣ 1. Goal

Use Power Query Advanced Editor to classify products into **Sales Tiers** based on their `Sales` value.

### **Sales Tiers**

| **Tier**  | **Range**             | **Why** |
|----------|------------------------|---------|
| Low      | $2.99 – $99.99         | Low-value items well below the mean |
| Mid      | $100 – $199.99         | Majority of sales (cluster near mode/mean) |
| High     | $200 – $499.99         | High-value but not extreme |
| Premium  | $500 – $899.88         | Rare, outlier-like sales |

**Full Documentation:**  
👉 https://docs.google.com/document/d/e/2PACX-1vQt4oKEMdnAltNa74DT_voiXhBuB1JhBGiWpqNFUpaigupY3DiPL3_DAbA3B00Gu_s0ponlnE7DO8LS/pub

---

## #️⃣ 2. Open Power Query → Advanced Editor

Go to:

**Home → Transform Data → Transform Data**

Then:

📌 **Advanced Editor**

**Screenshot:**  
![](./images_advancedEditor/click_advancededitor.jpg)

---

## #️⃣ 3. Original Query (Before Adding Sales Tier)

```m
let
    Source = Excel.Workbook(File.Contents("C:\095214Data\Connecting to Data\MyFootprintSportsSalesProducts.xlsx"), null, true),
    #"Sales Orders_Sheet" = Source{[Item="Sales Orders",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(#"Sales Orders_Sheet", [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{
        {"ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date},
        {"Ship Date", type date}, {"Shipping Method", type text}, {"Customer ID", type text},
        {"Product ID", type text}, {"Quantity", Int64.Type}, {"Sales", type number},
        {"Profit", type number}, {"Shipping Cost", type number}
    }),
    #"Reordered Columns" = Table.ReorderColumns(#"Changed Type",
        {"ID","Order ID","Order Date","Ship Date","Shipping Method",
         "Customer ID","Product ID","Quantity","Profit","Sales","Shipping Cost"})
in
    #"Reordered Columns"
```

**Screenshot (before):**  
![](./images_advancedEditor/BeforeProduct_Tiers.jpg)

---

## #️⃣ 4. Add Sales Tier in Advanced Editor

Insert this step before the final `in`:

```m
    #"Added Sales Tier" = Table.AddColumn(#"Reordered Columns", "SalesTier", each 
        if [Sales] >= 500 then "Premium"
        else if [Sales] >= 200 then "High"
        else if [Sales] >= 100 then "Mid"
        else "Low")
```

### ✔️ Final Code Block

```m
let
    Source = Excel.Workbook(File.Contents("C:\095214Data\Connecting to Data\MyFootprintSportsSalesProducts.xlsx"), null, true),
    #"Sales Orders_Sheet" = Source{[Item="Sales Orders",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(#"Sales Orders_Sheet", [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{
        {"ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date},
        {"Ship Date", type date}, {"Shipping Method", type text}, {"Customer ID", type text},
        {"Product ID", type text}, {"Quantity", Int64.Type}, {"Sales", type number},
        {"Profit", type number}, {"Shipping Cost", type number}
    }),
    #"Reordered Columns" = Table.ReorderColumns(#"Changed Type",
        {"ID","Order ID","Order Date","Ship Date","Shipping Method",
         "Customer ID","Product ID","Quantity","Profit","Sales","Shipping Cost"}),
    #"Added Sales Tier" = Table.AddColumn(#"Reordered Columns", "SalesTier", each 
        if [Sales] >= 500 then "Premium"
        else if [Sales] >= 200 then "High"
        else if [Sales] >= 100 then "Mid"
        else "Low")
in
    #"Added Sales Tier"
```

**Screenshot (after code update):**  
![](./images_advancedEditor/CodeAfterSalesTiersUpdate.jpg)

---

## #️⃣ 5. Verify the New Column

**Screenshot:**  
![](./images_advancedEditor/DataPane_newColumn.jpg)

---

## #️⃣ 6. Load the Data

Power BI:  
**Home → Close & Apply**

**Screenshot:**  
![](./images_advancedEditor/RefreshPreview.jpg)

---

## #️⃣ 7. Create a Custom Function

### Step 1 — Create Blank Query

Home → New Source → **Blank Query**  
Right-click → **Advanced Editor**

Paste:

```m
(Sales as number) as text =>
let
    Tier =
        if Sales >= 500 then "Premium"
        else if Sales >= 200 then "High"
        else if Sales >= 100 then "Mid"
        else "Low"
in
    Tier
```

**Screenshot:**  
![](./images_advancedEditor/Function_SalesTier.jpg)

Rename: **fnSalesTier**

---

## #️⃣ 8. Apply Function to Sales Column

Add Column → **Invoke Custom Function**

Settings:

- Name: **SalesTier_fn**  
- Function: **fnSalesTier**  
- Column: **Sales**

**Screenshot:**  
![](./images_advancedEditor/invoke_fn_Salestier.jpg)

Generated M code:

```m
= Table.AddColumn(#"Previous Step", "SalesTier_fn", each fnSalesTier([Sales]))
```

---

## #️⃣ 9. Compare Results

**Screenshot:**  
![](./images_advancedEditor/compareValues.jpg)
