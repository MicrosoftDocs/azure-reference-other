---
title: "Join Data | Microsoft Docs"
ms.custom: ""
ms.date: 10/05/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 124865f7-e901-4656-adac-f4cb08248099
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Join Data
*Joins two datasets*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
##  <a name="Remarks"></a> Module Overview  

This article describes how to use the [Join Data](join-data.md) module in Azure Machine Learning Studio to merge two datasets using a database-style *join operation*.  

To perform a join on two datasets, they must be related by a single key column. Composite keys are not supported. 

## How to Use Join Data

1. in Azure Machine Learning Studio, add the datasets you want to combine, and then drag the **Join Data** module into your experiment. You can find the module in the **Data Transformation** category, under **Manipulation**.

    Connect the datasets to the **Join Data** module. 
    
    The **Join Data** module does not support a right outer join, so if you want to ensure that rows from a particular dataset are included in the output, that dataset must be on the lefthand input.
  
2. Click **Launch column selector** to choose a single key column for the dataset on the left input.

3. Click **Launch column selector** to choose a single key column for the dataset on the right input.

4. Select the **Match case** option if you are joining on a text column and want to ensure that the join preserves case sensitivity. For example, if you deselect this option, `A1000` would be considered a different key value than `a1000`.

    If you deselect this option, `A1000` would be considered the same as `a1000`.
   
5. Use the **Join type** dropdown list to specify how the datasets should be combined. types:  
  
    - **Inner Join**. An *inner join* is the typical join operation. It returns the combined rows only when the values of the key columns match.  
  
    - **Left Outer Join**. A *left outer join* returns joined rows for all rows from the left table. When a row in the left table has no matching rows in the right table, the returned row contains missing values for all columns that come from the right table unless you specify a replacement value for missing values.  
  
    - **Full Outer Join**. A *full outer join* returns all rows from the left table (**table1**) and from the right table (**table2**).  
  
         For each of the rows in the left table that have no matching rows in the right table, the join results include a row containing missing values from the right table.  
  
         For each of the rows in the right table that have no matching rows in the left table, the join results include a row containing missing values for all columns from the left table.  
  
    - **Left Semi-Join**. A *left semi-join* returns only the values from the left table when the values of the key columns match.  

6. For the option, **Keep right key colums in joined table**:

    + Deselect the option to get a single key column in the results.
    + Leave the option selected to view the keys from both input tables. 

7. Run the experiment, or select the Join Data module and selected **Run Selected**, to perform the join.

7. To view the results, right-click the **Join Data** module, select **Results dataset**, and click **Visualize**.

  
> [!TIP]
> If your dataset has no key column, you can still combine it with another dataset, by using the [Add Columns](add-columns.md) module. This module functions more like R, and can combine two datasets on a row-by-row basis.
  
## Examples  
 You can see examples of how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   In the [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726) sample, [Join Data](join-data.md) is used to combine the positive training cases with the negative training cases after the proportion of cases has been adjusted.  
  
-   In the [Flight delay prediction](http://go.microsoft.com/fwlink/?LinkId=525725) sample, [Join Data](join-data.md) is used to bring together useful features from external datasets.  
  
-   In the [Movie recommendation](http://go.microsoft.com/fwlink/?LinkId=525276) sample, the datasets are joined so that we can present the recommended movie titles rather than a movie ID.  
  
-   In the [Prediction of student performance](http://go.microsoft.com/fwlink/?LinkId=525727) sample, [Join Data](join-data.md) is used to bring in new features.  
  
##  <a name="Notes"></a> Technical Notes  
  
-   The combined dataset cannot have two columns with the same name. Therefore, if the left and right datasets have any duplicate column names, a numeric suffix is appended to the column names of the right dataset to make them unique. For example, if both datasets had a column named Month, the column from the left dataset would remain as is, and the column from the right dataset would be renamed Month (1).  
  
-   The algorithm that is used for comparison of key values is hash-forced.  
  
-   Each column of the joined dataset preserves a categorical type, if the corresponding column of the input dataset is categorical.  
  
-   In left outer joins, if there are any missing values, a categorical level is created in the left dataset for missing values. This is true even if there are no missing values in the joined (right) dataset.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset1|[Data Table](data-table.md)|First dataset to join|  
|Dataset2|[Data Table](data-table.md)|Second dataset to join|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Join key columns for L|Any|ColumnSelection||Select the join key columns for the first dataset.|  
|Join key columns for R|Any|ColumnSelection||Select the join key columns for the second dataset.|  
|Match case|Any|Boolean|True|Indicate whether a case-sensitive comparison is allowed in key columns.|  
|Join type|List|Type|Inner join|Choose a join type.|  
|Keep right key columns in joined table|Any|Boolean|True|Indicate whether to keep key columns from the second dataset in the joined dataset.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Result of join operation|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](error-0001.md)|An exception occurs if one or more specified columns of the dataset couldn't be found.|  
|[Error 0003](error-0003.md)|An exception occurs if one or more inputs are null or empty.|  
|[Error 0006](error-0006.md)|An exception occurs if the parameter is greater than or equal to the specified value.|  
|[Error 0016](error-0016.md)|An exception occurs if the input datasets that are passed to the module should have compatible column types, but they do not.|  
|[Error 0017](error-0017.md)|An exception occurs if one or more specified columns have types that are unsupported by the current module.|  
|[Error 0020](error-0020.md)|An exception occurs if the number of columns in some of the datasets that are passed to the module is too small.|  
|[Error 0028](error-0028.md)|An exception occurs when the column set contains duplicate column names and it is not allowed.|  
|[Error 0011](error-0011.md)|An exception occurs if the argument for the passed column set does not apply to any dataset columns.|  
|[Error 0027](error-0027.md)|An exception occurs when two objects have to be of the same size, but they are not.|  
  
## See Also  
 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)