# ⚡ Advanced Editor & Custom Functions in M

## 📌 Core Objectives Covered
* **Built Reusable Power Query Custom Functions:** Encapsulated conditional sales tiering logic inside a single, central M function (`fnSalestier`) rather than rewriting rules across multiple queries.
* **Used M Language in Advanced Query Editor:** Hand-coded native M script inside Power Query's Advanced Editor to manage parameter types, conditional logic, and column operations directly.
* **Reduced Repetitive Transformations:** Replaced multi-step inline column calculations across different tables with a single, streamlined function invocation step.
* **Improved Scalability and Maintainability:** Ensured that future business updates (like changing sales threshold amounts) only need to be modified once inside the primary function to update all dependent queries automatically.

---

## 🛠️ Step-by-Step Execution & Breakdown

### 1️⃣ Advanced Editor & Base Code Setup
* **Opening the Script:** Accessed the Advanced Editor from the **View** ribbon to inspect the raw `let ... in` M structure for the `Sales Orders` query (`click_advancededitor.jpg`, `BeforeProduct_Tiers.jpg`).
* **Manual Logic Entry:** Hand-coded an inline `Table.AddColumn` step using `if/else` conditions to classify orders into "Premium", "High", "Mid", and "Low" tiers based on sales volume (`CodeAfterSalesTiersUpdate.jpg`).
* **Validation:** Reordered the new `SalesTier` column next to the numerical `Sales` column to verify output correctness in the data grid (`AfterSalesTiersUpdate.jpg`).

### 2️⃣ Custom Function Construction (`fnSalestier`)
* **Creating Blank Query:** Navigated to **Home** > **New Source** > **Blank Query** to construct a standalone query container (`Home_BlankQuery.jpg`).
* **Writing the Function Signature:** Used M code in the Advanced Editor to define a function accepting a decimal parameter (`Sales as nullable number`) and returning the matching tier string (`Function_SalesTier.jpg`).
* **Naming and Storing:** Saved the query object as `fnSalestier` in the query pane for global reuse (`saveMyFunction.jpg`).

### 3️⃣ Function Testing & Invocation
* **Parameter Testing:** Verified the function logic independently by inputting static test values into the function interface to confirm accurate output generation (`Testingparameter.jpg`, `InvokedFunction.jpg`).
* **Invoking on Query:** Returned to the primary dataset, navigated to **Add Column** > **Invoke Custom Function**, and selected `fnSalestier` (`SelectCustomColumn.jpg`, `SelectCustomerFunction.jpg`).
* **Parameter Mapping:** Configured the input mode from static text to **Column Name**, mapping the function parameter directly to the `Sales` decimal field (`checkDecimalValue.jpg`, `SelectSaleAsParameter.jpg`, `invoke_fn_Salestier.jpg`).

### 4️⃣ Output Parity & Cross-Table Scaling
* **Cross-Checking Results:** Placed the direct inline column (`SalesTier`) side-by-side with the custom function result (`SalesTier_fn`) to confirm 100% data parity (`compareValues.jpg`, `ApplySubsequentsteps.jpg`).
* **Scaling to Historical Tables:** Applied the same transformation pattern to secondary historical tables (such as `Sales Orders2019-2020`) using M code re-use, eliminating the need to rebuild steps manually from the GUI (`Copy_replace.jpg`, `AddCodeCodetoSalesOrder2ndtable.jpg`, `Result_2ndTable.jpg`, `RefreshPreview.jpg`).

### 5️⃣ Data View & Model Finalization
* **Data Type Formatting:** Converted the `Sales` column to **Decimal Number** (formatted to 2 decimal places) in the Power BI Desktop Data View to ensure proper presentation (`ConvertSalesToDecimal.jpg`).
* **Fields Pane Verification:** Confirmed that the new calculated custom function columns loaded seamlessly into the Desktop Fields Pane for use in visuals and downstream reporting (`DataPane_newColumn.jpg`, `ViewNewColumninPBI.jpg`, `loanNewColumn.jpg`).
