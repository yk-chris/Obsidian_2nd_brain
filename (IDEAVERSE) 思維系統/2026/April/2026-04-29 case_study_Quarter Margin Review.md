### Quarter Margin Review
#### Purpose
> Aims to evaluate the engine with  Engine Type | Work Type. Once the engine is defined as a outliner, the reason is needed to be provided. 
> But not all engines would be considered on the margin review - selected work type like MFR /1FR

#### Costing category
1. Materials (Customer reservation or not)
2. Sub-contract
3. Man-hours

#### Procedural Operations
1. to dip into the outliner engine in terms of Engine Type | Work Type from the nearly current invoice list in comparison with the previous budgeting pool (like ESV) 
2. The reasons vary at three categories such materials, sub-contract & man-hours from engine repair
3. to individually find the reasons respective of materials, sub-contract & man-hours pool. 
4. to standardize the apple-to-apple data set to minimize the issues like discounting from period to period
5. **to dive deep into the significance of items in terms of material items.**

	**Step 1** - Extract the Top N (for example, 50) material items with the largest values from each engine in the previous engine pool (such as ESV), categorized by engine type and work type.  
	**Step 2** - Combine these into a list of significant material items across all engines.  
	**Step 3** - Calculate the aggregate value using this list of significant material items, and compare it with the selected engine.

6. to compare items across three costing categories


### Feature: to create a quarter material review analysis
GIVEN "Material_ISP_budget" and "Material_ISP_actual" sheet is stated on the Excel

```
### Definition
- A material item is defined by the combination of Module (found in column AX), IPC Location (found in column AA), PartNo (found in column N), and PartDesc (found in column O).

### Contraint
- PartNo must be converted into "Text" format instead of a number
- IPC Location must be converted into "Text" format instead of a number
  
### Procedure
// to add Ranking column on each engine
From the sheet named "Material_ISP_budget", to create individual sheets by unique "EngineSerialNumber" located in column B and each sheet is named by EngineSerialNumber. Moreover, to put a series of columns including | EngineType | Work LV | SalesOrder | EngineSerialNumber | CustomerCode | ValType | Appendix | Module | IPC Location | PartNo | PartDesc | Qty | SapUnitPrice | PoUnitPrice | Discount Selling Price | on each EngineSerialNumber sheet 
AND add one more column named "Rank" to calculate each row to rank it as 1 if "Discount Selling Price" located in column W is the largest value and so on.

// to construct the Top-rank consolidation sheet
Afterwards, create a new sheet named "TopRank_{EngineType}_{Work LV}" that combines a series of unique material items from each row within the Top 50 ranking of every "EngineSerialNumber" sheet with columns of | Module | IPC Location | PartNo | PartDesc | ...

Within "TopRank_{EngineType}_{Work LV}" sheet, to continue to 
1. add a column named "located_sheet" to specify which sheet is included for each material item and a column named "number_occurrence" to count for how many EngineSerialNumber included each material item
2. add a column named "Avg_QTY" to calculate average QTY from the total QTY (located in column Q) to divide by how many engine is count on this EngineType and Work LV
3. add a column named "Avg_SapUnitPrice" to calculate average SapUnitPrice from the total SapUnitPrice (located in column AR) to divide by how many engine is count on this EngineType and Work LV
4. add a column named "Avg_PoUnitPrice" to calculate average PoUnitPrice from the total PoUnitPrice (located in column AS) to divide by how many engine is count on this EngineType and Work LV
5. add a column named "Avg_DiscountSellingPrice" to calculate average Discount Selling Price from the total Discount Selling Price (located in column W) to divide by how many engine is count on this EngineType and Work LV

// to add ranking on the ranking column 
Form the original "Material_ISP_actual" sheet, 

Add an additional column called "Rank_actual" to rank each row as 1 within each EngineSerialNumber in column B if the "Discount Selling Price" in column W is the highest value, and continue ranking accordingly. Exclude any rows where the "IPC Location" in column AA starts with 'TR' from the ranking process.

// to find the difference between each engine from actual vs budget
To create a new sheet named "materials_actual_budget" to extract the full table from "Material_ISP_actual" with following columns of | EngineType | Work LV | SalesOrder | EngineSerialNumber | Module | IPC Location | PartNo | PartDesc | Appendix | Rank_actual | ...

From this "materials_actual_budget" sheet, 

1. Add a column called "avg_QTY_budget" to reference "avg_QTY" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
2. Add a column called "diff_QTY" that calculates the difference by subtracting "QTY" from "avg_QTY_budget".
3. Add a column called "Avg_PoUnitPrice_budget" to reference "Avg_PoUnitPrice" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
4. Add a column called "diff_PoUnitPrice" that calculates the difference by subtracting "PoUnitPrice" from "avg_PoUnitPrice_budget".
5. Add a column called "avg_DiscountSellingPrice_budget" to reference "avg_DiscountSellingPrice" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
6. Add a column called "diff_DiscountSellingPrice" that calculates the difference by subtracting "Discount Selling Price" from "avg_DiscountSellingPrice_budget".

   
```

###  Revised version
```

### Definition
- A material item is defined by the combination of Module (found in column AX), IPC Location (found in column AA), PartNo (found in column N), and PartDesc (found in column O).

### Contraint
- PartNo must be converted into "Text" format by adding "'" before the number to avoid scientific (E) notation issue after Text conversion
- IPC Location must be converted into "Text" format instead of a number
- Module must be converted by mapping table as below:
  {
	"01":"M31","02":"M32","03":"M33","04":"M41",
	"05":"M51",
	"06":"M61",
	"07":"M34",
	"08":"M52"
  }
- to convert "QTY" to the "0.0" format within a list like ['QTY', 'avg_QTY','diff_QTY']
- to convert "Price" to the "$#,##0.00_);[Red]($#,##0.00)" format within a list like ['SapUnitPrice','Avg_SapUnitPrice','PoUnitPrice','diff_PoUnitPrice','Discount Selling Price','avg_DiscountSellingPrice','diff_DiscountSellingPrice']
- to have the columns automatically adjust to fit the width

### Procedure
// to add Ranking column on each engine
From the sheet named "Material_ISP_budget", to create individual sheets by unique "EngineSerialNumber" located in column B and each sheet is named by EngineSerialNumber. Moreover, to put a series of columns including | EngineType | Work LV | SalesOrder | EngineSerialNumber | CustomerCode | ValType | Appendix | Module | IPC Location | PartNo | PartDesc | Qty | SapUnitPrice | PoUnitPrice | Discount Selling Price | on each EngineSerialNumber sheet 
AND add one more column named "Rank" to calculate each row to rank it as 1 if "Discount Selling Price" located in column W is the largest value and so on.

// to construct the Top-rank consolidation sheet
Afterwards, create a new sheet named "TopRank_{EngineType}_{Work LV}" that combines a series of unique material items from each row within the Top 50 ranking of every "EngineSerialNumber" sheet with columns of | Module | IPC Location | PartNo | PartDesc | ...

Within "TopRank_{EngineType}_{Work LV}" sheet, to continue to 
1. add a column named "located_sheet" to specify which sheet is included for each material item and a column named "number_occurrence" to count for how many EngineSerialNumber included each material item
2. add a column named "Avg_QTY" to calculate average QTY from the total QTY (located in column Q) to divide by how many engine is count on this EngineType and Work LV
3. add a column named "Avg_SapUnitPrice" to calculate average SapUnitPrice from the total SapUnitPrice (located in column AR) to divide by how many engine is count on this EngineType and Work LV
4. add a column named "Avg_PoUnitPrice" to calculate average PoUnitPrice from the total PoUnitPrice (located in column AS) to divide by how many engine is count on this EngineType and Work LV
5. add a column named "Avg_DiscountSellingPrice" to calculate average Discount Selling Price from the total Discount Selling Price (located in column W) to divide by how many engine is count on this EngineType and Work LV

// to add ranking on the ranking column 
Form the original "Material_ISP_actual" sheet, 

Add an additional column called "Rank_actual" to rank each row as 1 within each EngineSerialNumber in column B if the "Discount Selling Price" in column W is the highest value, and continue ranking accordingly. Exclude any rows where the "IPC Location" in column AA starts with 'TR' from the ranking process.

// to find the difference between each engine from actual vs budget
To create a new sheet named "materials_actual_budget" to extract the full table from "Material_ISP_actual" with following columns of | EngineType | Work LV | SalesOrder | EngineSerialNumber | Module | IPC Location | PartNo | PartDesc | Appendix | Rank_actual | ...

From this "materials_actual_budget" sheet, 

1. Add a column called "TOP50 with ESV" and Check if the material item exists in both "Material_ISP_actual" sheet and one of these "TopRank_{EngineType}_{Work LV}" sheets at the same time.
2. Add a column called "avg_QTY_budget" to reference "avg_QTY" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
3. Add a column called "diff_QTY" that calculates the difference by (= "QTY" - "avg_QTY_budget").
4. Add a column called "Avg_PoUnitPrice_budget" to reference "Avg_PoUnitPrice" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
5. Add a column called "diff_PoUnitPrice" that calculates the difference by (= "PoUnitPrice" - "avg_PoUnitPrice_budget").
6. Add a column called "avg_DiscountSellingPrice_budget" to reference "avg_DiscountSellingPrice" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
7. Add a column called "diff_DiscountSellingPrice" that calculates the difference by ("Discount Selling Price" - "avg_DiscountSellingPrice_budget").
8. From the sheet named "materials_actual_budget", to create individual sheets by unique "EngineSerialNumber" located in column B and each sheet is named by EngineSerialNumber_Q1. Sorting by "diff_DiscountSellingPrice"(located on U column).


```


```
//after checking
Remove all formulas from every cell and replace them with their corresponding values across all sheets.
```

```
// give an insight summary
## Task: 
Generate an Insight Summary for Engine [ENGINE_SERIAL_NUMBER] [PERIOD] (Actual vs Budget) The active sheet is **'[SHEET_NAME]'** (e.g., `41393_Q1`).
 
### Expected Column Layout (Columns A–U) 
| Col | Header | Description | 
|-----|--------|-------------| 
| A | EngineType | e.g., TRENT700 | 
| B | Work LV | e.g., 1FR | 
| C | SalesOrder | Sales order number | 
| D | EngineSerialNumber | Engine serial number | 
| E | Module | Module code (1–8, NM) | 
| F | IPC Location | IPC location reference | 
| G | PartNo | Part number | 
| H | PartDesc | Part description | 
| I | Appendix | Valuation type: "C" = Customer Serviceable, any value starting with "T" (T, T1, T4) = New/Replacement | 
| J | Rank_actual | Rank from actual data | 
| K | Qty | Actual quantity | 
| L | SapUnitPrice | SAP unit price | 
| M | PoUnitPrice | PO unit price | 
| N | Discount Selling Price | Actual discount selling price (primary value column) | 
| O | TOP50 with ESV | "Yes" or "No" flag indicating whether item is a TOP 50 part | 
| P | avg_QTY_budget | Average budget quantity | 
| Q | diff_QTY | Quantity variance (budget avg minus actual; positive means budget was higher) | 
| R | Avg_PoUnitPrice_budget | Average budget PO unit price | 
| S | diff_PoUnitPrice | PO unit price variance (budget avg minus actual) | 
| T | avg_DiscountSellingPrice_budget | Average budget discount selling price | 
| U | diff_DiscountSellingPrice | Selling price variance (budget avg minus actual; negative means actual exceeded budget) | 
> **Note:** The active sheet already has columns A–U populated with data. The insight summary should be built in **columns W–AB** starting at row 1, using Excel formulas that reference columns A–U. Auto-detect the last row of data dynamically. 
--- 

### Insight Summary Sections to Build (in columns W–AB, starting row 1) Build each section sequentially. Use section header emoji labels. Format currency as `$#,##0.00` and percentages as `0.0%`. 
--- 

#### 1. 📋 HEADER (Row 1) 
- Place a title: **"INSIGHT SUMMARY — Engine [ESN] [PERIOD] Actual vs Budget"** 
- Pull the ESN value from the data itself (column D). 
#### 2. 📋 OVERVIEW (starting ~Row 3) Build a label/value table with: 
- **Engine Type** — pull from the first data row of column A 
- **Engine Serial Number** — pull from the first data row of column D 
- **Sales Order** — pull from the first data row of column C 
- **Work Level** — pull from the first data row of column B 
- **Total Line Items** — count all non-empty rows in the data (exclude header) 
- **Unique Part Numbers** — count distinct values in the PartNo column 
#### 3. 📊 APPENDIX BREAKDOWN (starting ~Row 12) 
Build a table: **Appendix | Count | Total Disc. Selling Price | % of Total** Three rows: 
- **C (Customer Serviceable)** 
— count and sum selling price where Appendix = "C" 
- **T (New / Replacements)** 
— count and sum selling price where Appendix starts with "T" (covers T, T1, T4 variants; use wildcard matching) 
- **TOTAL** 
— sum of the above two rows; percentage should equal 100% 
#### 4. 🏆 TOP 50 vs NON-TOP 50 (starting ~Row 18) 
Build a table: **Category | Count | Total Disc. Selling Price | % of Total** Three rows: 
- **TOP 50 (with ESV)** 
— count and sum selling price where the TOP50 flag = "Yes" 
- **Non-TOP 50** — count and sum selling price where the TOP50 flag = "No" 
- **TOTAL** — sum of the above two rows 
#### 5. 📈 ACTUAL vs BUDGET VARIANCE — TOP 50 Items (starting ~Row 24) 
Build a table: **Metric | Avg Actual | Avg Budget | Avg Variance** Three rows, each averaging only rows where TOP50 flag = "Yes": 
- **Quantity** 
— average of actual Qty, average of budget Qty, average of Qty variance 
- **PO Unit Price** 
— average of actual PO price, average of budget PO price, average of PO price variance 
- **Disc. Selling Price** 
— average of actual selling price, average of budget selling price, average of selling price variance 
#### 6. 🔧 MODULE BREAKDOWN (starting ~Row 30) 
Build a table: **Module | Item Count | Total Disc. Selling Price** One row per distinct module value found in column E (typically: 1, 2, 3, 4, 5, 6, 7, 8, NM). For each: 
- Count rows belonging to that module - Sum the selling price for that module 
- Add a TOTAL row at the bottom 
#### 7. 💰 TOP 10 HIGHEST VALUE ITEMS (after Module section) 
Build a table: **Rank | PartNo | PartDesc | Module | Qty | Discount Selling Price** Find the 10 items with the largest Discount Selling Price. For each rank (1–10): 
- Look up the corresponding PartNo, PartDesc, Module, and Qty from the row with the k-th largest selling price 

#### 8. ⚠️ VARIANCE HIGHLIGHTS (after Top 10 section) Build a label/value summary with: 
- **Items where actual Qty exceeds budget avg** 
— count rows where the Qty variance is negative (actual > budget) 
- **Items where actual Qty is below budget avg** — count rows where the Qty variance is positive - **Items where actual Selling Price exceeds budget** 
— count rows where the Selling Price variance is negative 
- **Items where actual Selling Price is below budget** — count rows where the Selling Price variance is positive 
- **Total Actual Disc. Selling Price** — sum of all selling prices in column N 
- **Total Budget Avg Disc. Selling Price (TOP50)** — sum of budget selling price for TOP50-flagged items only 
- **Net Variance (TOP50, Actual − Budget)** 
— total actual selling price for TOP50 items minus total budget selling price for TOP50 items 
--- 

### Formatting Requirements 
- Use **emoji section headers** (📋, 📊, 🏆, 📈, 🔧, 💰, ⚠️) in column W 
- Format all dollar amounts as `$#,##0.00` - Format all percentages as `0.0%` 
- Bold all section headers and table column headers - All values must be **live formulas** referencing columns A–U (no hard-coded numbers) 

### After Building the Summary Provide a **narrative summary** highlighting: 
1. Cost concentration (Pareto analysis — what % of items drive what % of cost) 
2. Which module dominates by cost 
3. Budget overrun or underrun magnitude and direction 
4. What percentage of TOP-50 items exceeded their budget benchmark on selling price 
   
### Key Assumptions 
- Auto-detect the last row by counting non-empty cells in column A 
- The TOP50 flag column contains exactly "Yes" or "No" 
- Appendix column uses "C" for customer-serviceable; anything starting with "T" for new parts 
- Variance columns are calculated as **budget minus actual** (positive = budget higher, negative = actual exceeded budget)
  
```