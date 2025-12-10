"# Sales Tier Custom Function Guide

This guide shows how to create and apply a **custom M function** in Power BI to categorize Sales into tiers.

---

## 1️⃣ Create Parameters (Optional)
If using parameters for tier thresholds:

- **LowMax**
- **MidMax**
- **HighMax**
- **PremiumMin**

*(If not using parameters, skip to step 2.)*

---

## 2️⃣ Create a Custom Function

**Home → New Source → Blank Query**

Rename the query to: `fnSalesTier`

Then open:

**View → Advanced Editor**

Paste the function:

```m
// fnSalesTier – Returns tier based on Sales value
(Sales as number) as text =>
let
    Tier =
        if Sales >= 500 then "Premium"       // $500 – $899.88
        else if Sales >= 200 then "High"     // $200 – $499.99
        else if Sales >= 100 then "Mid"      // $100 – $199.99
        else "Low"                           // $2.99 – $99.99
in
    Tier
Save the query.

3️⃣ Apply the Function to Your Table
Go to the table containing your Sales column.

Add Column → Invoke Custom Function

Settings:

Field	Value
New Column Name	SalesTier
Function Query	fnSalesTier
Sales Column Input	Sales

This will generate a new column titled SalesTier in your table.

4️⃣ Load the Data
Power BI:

Home → Close & Apply

Excel Power Query:

Home → Close & Load

5️⃣ Result
Your data now has a clean categorical field:

Low

Mid

High

Premium