# ⚡ Advanced Editor & Custom Functions in M

## 📌 Core Objectives Covered
* **Built Reusable Power Query Custom Functions:** Encapsulated conditional sales tiering logic inside a single, central M function (`fnSalestier`) rather than rewriting rules across multiple queries.
* **Used M Language in Advanced Query Editor:** Hand-coded native M script inside Power Query's Advanced Editor to manage parameter types, conditional logic, and column operations directly.
* **Reduced Repetitive Transformations:** Replaced multi-step inline column calculations across different tables with a single, streamlined function invocation step.
* **Improved Scalability and Maintainability:** Ensured that future business updates (like changing sales threshold amounts) only need to be modified once inside the primary function to update all dependent queries automatically.

---

## 🛠️ Step-by-Step Execution & Breakdown

### 1️⃣ Advanced Editor & Base Code Setup
* **Opening the Script:** Accessed the Advanced Editor from the **View** ribbon to inspect the raw `let ... in` M structure for the `Sales Orders` query.
* **Manual Logic Entry:** Hand-coded an inline `Table.AddColumn` step using `if/else` conditions to classify orders into "Premium", "High", "Mid", and "Low" tiers based on sales volume.
* **Validation:** Reordered the new `SalesTier` column next to the numerical `Sales` column to verify output correctness in the data grid.

![Click Advanced Editor](images_advancedEditor/click_advancededitor.jpg)
![Before Custom Tiers Code](images_advancedEditor/BeforeProduct_Tiers.jpg)
![Code After Sales Tiers Update](images_advancedEditor/CodeAfterSalesTiersUpdate.jpg)
![Grid View After Sales Tiers Update](images_advancedEditor/AfterSalesTiersUpdate.jpg)

---

### 2️⃣ Custom Function Construction (`fnSalestier`)
* **Creating Blank Query:** Navigated to **Home** > **New Source** > **Blank Query** to construct a standalone query container.
* **Writing the Function Signature:** Used M code in the Advanced Editor to define a function accepting a decimal parameter (`Sales as nullable number`) and returning the matching tier string.
* **Naming and Storing:** Saved the query object as `fnSalestier` in the query pane for global reuse.

![Home Blank Query](images_advancedEditor/Home_BlankQuery.jpg)
![Function Sales Tier Definition](images_advancedEditor/Function_SalesTier.jpg)
![Save Custom Function](images_advancedEditor/saveMyFunction.jpg)

---

### 3️⃣ Function Testing & Invocation
* **Parameter Testing:** Verified the function logic independently by inputting static test values into the function interface to confirm accurate output generation.
* **Invoking on Query:** Returned to the primary dataset, navigated to **Add Column** > **Invoke Custom Function**, and selected `fnSalestier`.
* **Parameter Mapping:** Configured the input mode from static text to **Column Name**, mapping the function parameter directly to the `Sales` decimal field.

![Testing Parameter Value](images_advancedEditor/Testingparameter.jpg)
![Invoked Function Test Output](images_advancedEditor/InvokedFunction.jpg)
![Select Custom Column Dialog](images_advancedEditor/SelectCustomColumn.jpg)
![Select Function Name](images_advancedEditor/SelectCustomerFunction.jpg)
![Check Decimal Parameter Type](images_advancedEditor/checkDecimalValue.jpg)
![Select Sales as Parameter](images_advancedEditor/SelectSaleAsParameter.jpg)
![Invoke Custom Function Final Step](images_advancedEditor/invoke_fn_Salestier.jpg)

---

### 4️⃣ Output Parity & Cross-Table Scaling
* **Cross-Checking Results:** Placed the direct inline column (`SalesTier`) side-by-side with the custom function result (`SalesTier_fn`) to confirm 100% data parity.
* **Scaling to Historical Tables:** Applied the same transformation pattern to secondary historical tables (such as `Sales Orders2019-2020`) using M code re-use, eliminating the need to rebuild steps manually from the GUI.

![Comparing Inline vs Custom Function Values](images_advancedEditor/compareValues.jpg)
![Full M Script with Invoked Steps](images_advancedEditor/ApplySubsequentsteps.jpg)
![Find and Replace M Code Scripting](images_advancedEditor/Copy_replace.jpg)
![Add Code to Second Table](images_advancedEditor/AddCodeCodetoSalesOrder2ndtable.jpg)
![Result 2nd Table Preview](images_advancedEditor/Result_2ndTable.jpg)
![Refresh Preview](images_advancedEditor/RefreshPreview.jpg)

---

### 5️⃣ Data View & Model Finalization
* **Data Type Formatting:** Converted the `Sales` column to **Decimal Number** (formatted to 2 decimal places) in the Power BI Desktop Data View to ensure proper presentation.
* **Fields Pane Verification:** Confirmed that the new calculated custom function columns loaded seamlessly into the Desktop Fields Pane for use in visuals and downstream reporting.

![Converting Sales Column to Decimal in Data View](images_advancedEditor/ConvertSalesToDecimal.jpg)
![View New Column in Power BI Data Pane](images_advancedEditor/DataPane_newColumn.jpg)
![Verify Field List Display](images_advancedEditor/ViewNewColumninPBI.jpg)
![Loan New Column Check](images_advancedEditor/loanNewColumn.jpg)
