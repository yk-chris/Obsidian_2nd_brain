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

###  Karen version
```

### Definition
- A material item is defined by the combination of Module (found in column AX), IPC Location (found in column AA), PartNo (found in column N), and PartDesc (found in column O).

### Contraint
- PartNo must be converted into "Text" format instead of a number
- IPC Location must be converted into "Text" format instead of a number
- to convert "QTY" to the "#.#" format within a list like ['QTY', 'avg_QTY','diff_QTY']
- to convert "Price" to the "$#,##0.00" format within a list like ['SapUnitPrice','Avg_SapUnitPrice','PoUnitPrice','diff_PoUnitPrice','Discount Selling Price','avg_DiscountSellingPrice','diff_DiscountSellingPrice']
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
3. Add a column called "diff_QTY" that calculates the difference by subtracting "QTY" from "avg_QTY_budget".
4. Add a column called "Avg_PoUnitPrice_budget" to reference "Avg_PoUnitPrice" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
5. Add a column called "diff_PoUnitPrice" that calculates the difference by subtracting "PoUnitPrice" from "avg_PoUnitPrice_budget".
6. Add a column called "avg_DiscountSellingPrice_budget" to reference "avg_DiscountSellingPrice" once the material items are matched from the "TopRank_{EngineType}_{Work LV}" sheets, ensuring the same EngineType and Work LV are used.
7. Add a column called "diff_DiscountSellingPrice" that calculates the difference by subtracting "Discount Selling Price" from "avg_DiscountSellingPrice_budget".
8. From the sheet named "materials_actual_budget", to create individual sheets by unique "EngineSerialNumber" located in column B and each sheet is named by EngineSerialNumber_Q1.Sorting by “Rank”(located on J column).

```


```
//after checking
Remove all formulas from every cell and replace them with their corresponding values across all sheets.
```

