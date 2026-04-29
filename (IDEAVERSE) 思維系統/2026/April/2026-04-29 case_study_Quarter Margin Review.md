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


```
### Definition
- A material item is combined from IPC Location (located in column AA), PartNo (located in column N) and PartDesc (located in column O)


### Procedure
// to add Ranking column on each engine
From the sheet named "Material_ISP_budget", to create individual sheets by unique "EngineSerialNumber" located in column B and each sheet is named by EngineSerialNumber. Moreover, to put a series of columns including | EngineType | Work LV | SalesOrder | EngineSerialNumber | CustomerCode | ValType | IPC Location | PartNo | PartDesc | Appendix | Qty | SapUnitPrice | PoUnitPrice | Discount Selling Price |  on each EngineSerialNumber sheet 
AND add one more column named "Rank" to calculate each row to rank it as 1 if "Discount Selling Price" located in column W is the largest value and so on.

// to construct the Top50-rank consolidation sheet
After that , to combine a series of unique material items on a new sheet called "Top50_{EngineType}_{Work LV}" from Top 50 ranking of all sheets of "EngineSerialNumber" with columns of | Module | IPC Location | PartNo | PartDesc | ...

Within "Top50_{EngineType}_{Work LV}" sheet, 
1. add a column named "located_sheet" to specify which sheet is included for each material item and a column named "number_occurrence" to count for how many EngineSerialNumber included each material item
2. add a column named "Avg_QTY" to calculate average QTY from Total QTY (located in column Q) to divide by how many engine is count on this EngineType and Work LV
3. add a column named "Avg_SapUnitPrice" to calculate average SapUnitPrice from Total SapUnitPrice (located in column AR) to divide by how many engine is count on this EngineType and Work LV
4. add a column named "Avg_PoUnitPrice" to calculate average PoUnitPrice from Total PoUnitPrice (located in column AS) to divide by how many engine is count on this EngineType and Work LV
5. add a column named "Avg_DiscountSellingPrice" to calculate average PoUnitPrice from Total PoUnitPrice (located in column AS) to divide by how many engine is count on this EngineType and Work LV

// to find the difference on each engine from actual vs budget data in terms of QTY, price & Value

   
```



```
### Definition
- A material item is combined from Module (located in column AX), IPC Location (located in column AA), PartNo (located in column N) and PartDesc (located in column O)

Within "Top50_{EngineType}_{Work LV}" sheet, 
1. add a column named "located_sheet" to specify which sheet is included for each material item and a column named "number_occurrence" to count for how many EngineSerialNumber included each material item
2. add a column named "Avg_QTY" to calculate average QTY from Total QTY (located in column Q) to divide by a number of material items occurrence from all "EngineSerialNumber" 
3. add a column named "Avg_SapUnitPrice" to calculate average SapUnitPrice from Total SapUnitPrice (located in column AR) to divide by a number of material items occurrence from all "EngineSerialNumber" 
4. add a column named "Avg_PoUnitPrice" to calculate average PoUnitPrice from Total PoUnitPrice (located in column AS) to divide by a number of material items occurrence from all "EngineSerialNumber".
5. add a column named "Avg_DiscountSellingPrice" to calculate average PoUnitPrice from Total PoUnitPrice (located in column AS) to divide by a number of material 
```