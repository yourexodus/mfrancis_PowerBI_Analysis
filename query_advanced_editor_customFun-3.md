# ⚡ Advanced Editor & Custom Functions in M

## 📌 Core Objectives Covered
* **Built Reusable Power Query Custom Functions:** Encapsulated conditional sales tiering logic inside a single, central M function (`fnSalestier`) rather than rewriting rules across multiple queries.
* **Used M Language in Advanced Query Editor:** Hand-coded native M script inside Power Query's Advanced Editor to manage parameter types, conditional logic, and column operations directly.
* **Reduced Repetitive Transformations:** Replaced multi-step inline column calculations across different tables with a single, streamlined function invocation step.
* **Improved Scalability and Maintainability:** Ensured that future business updates (like changing sales threshold amounts) only need to be modified once inside the primary function to update all dependent queries automatically.

---

## 🛠️ Step-by-Step Execution & Breakdown

### 1️⃣ Advanced Editor & Base Code Setup

To review and modify the raw M transformations, open the **View** ribbon tab and select **Advanced Editor** to open the M script window.
![Click Advanced Editor](images_advancedEditor/click_advancededitor.jpg)

Before adding custom logic, inspect the original `let ... in` code structure of the `Sales Orders` query to identify where to insert custom transformations.
![Before Custom Tiers Code](images_advancedEditor/BeforeProduct_Tiers.jpg)

Hand-code an inline `Table.AddColumn` step using `if/else` logic to assign "Premium", "High", "Mid", and "Low" sales tiers directly inside the Advanced Editor.
![Code After Sales Tiers Update](images_advancedEditor/CodeAfterSalesTiersUpdate.jpg)

Save and exit the editor to verify that the newly generated `SalesTier` column appears alongside the numeric `Sales` column in the data grid.
![Grid View After Sales Tiers Update](images_advancedEditor/AfterSalesTiersUpdate.jpg)

---

### 2️⃣ Custom Function Construction (`fnSalestier`)

To build a central reusable custom function, navigate to **Home** > **New Source** > **Blank Query** to initialize a new query object.
![Home Blank Query](images_advancedEditor/Home_BlankQuery.jpg)

Open the Advanced Editor for the blank query and write the parameter definition `(Sales as nullable number)` along with the conditional M tiering script.
![Function Sales Tier Definition](images_advancedEditor/Function_SalesTier.jpg)

Rename and save the new query object as `fnSalestier` in the left Query Pane for cross-query access.
![Save Custom Function](images_advancedEditor/saveMyFunction.jpg)

---

### 3️⃣ Function Testing & Invocation

Before applying the custom function across datasets, input static numbers into the parameter input UI to verify that the function returns correct tier strings.
![Testing Parameter Value](images_advancedEditor/Testingparameter.jpg)

Review the standalone test output screen to confirm the custom function resolves the test values accurately.
![Invoked Function Test Output](images_advancedEditor/InvokedFunction.jpg)

Return to the `Sales Orders` dataset, open the **Add Column** tab, and select **Invoke Custom Function**.
![Select Custom Column Dialog](images_advancedEditor/SelectCustomColumn.jpg)

In the Invoke Custom Function dialog box, choose `fnSalestier` from the function dropdown menu.
![Select Function Name](images_advancedEditor/SelectCustomerFunction.jpg)

Verify that the expected decimal parameter type matches the data type of the underlying target field.
![Check Decimal Parameter Type](images_advancedEditor/checkDecimalValue.jpg)

Toggle the input setting from static text entry to **Column Name**, mapping the parameter directly to the `Sales` column.
![Select Sales as Parameter](images_advancedEditor/SelectSaleAsParameter.jpg)

Click **OK** to run the function and create the calculated custom column within the query environment.
![Invoke Custom Function Final Step](images_advancedEditor/invoke_fn_Salestier.jpg)

---

### 4️⃣ Output Parity & Cross-Table Scaling

Compare the direct inline calculated column `SalesTier` with the function-generated column `SalesTier_fn` side-by-side to ensure complete data parity.
![Comparing Inline vs Custom Function Values](images_advancedEditor/compareValues.jpg)

Inspect the finalized query M code script showing both the inline conditional steps and the invoked function steps combined.
![Full M Script with Invoked Steps](images_advancedEditor/ApplySubsequentsteps.jpg)

Copy the custom M code block using text editing techniques to easily port transformations across secondary queries.
![Find and Replace M Code Scripting](images_advancedEditor/Copy_replace.jpg)

Paste the custom transformation logic directly into the Advanced Editor of secondary historical datasets like `Sales Orders2019-2020`.
![Add Code to Second Table](images_advancedEditor/AddCodeCodetoSalesOrder2ndtable.jpg)

Check the data grid of the secondary table to confirm that the tiered calculations resolved correctly without recreating steps manually.
![Result 2nd Table Preview](images_advancedEditor/Result_2ndTable.jpg)

Execute a preview refresh across the Power Query Editor to ensure all table dependencies evaluate cleanly.
![Refresh Preview](images_advancedEditor/RefreshPreview.jpg)

---

### 5️⃣ Data View & Model Finalization

Switch to the Power BI Desktop Data View to update the `Sales` column formatting to **Decimal Number** with 2 decimal places.
![Converting Sales Column to Decimal in Data View](images_advancedEditor/ConvertSalesToDecimal.jpg)

Verify that the newly created custom function column appears under the correct table within the Power BI Desktop Fields pane.
![View New Column in Power BI Data Pane](images_advancedEditor/DataPane_newColumn.jpg)

Confirm that the calculated attribute is fully loaded into the report dataset view and ready for visual analysis.
![Verify Field List Display](images_advancedEditor/ViewNewColumninPBI.jpg)

Perform a final validation check across secondary related tables to ensure calculated attributes integrate cleanly throughout the data model.
![Loan New Column Check](images_advancedEditor/loanNewColumn.jpg)
