---
title: "Remove Duplicate Rows | Microsoft Docs"
ms.custom: ""
ms.date: 09/21/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 02016f47-e4c3-4a06-9ae5-16c747389e34
caps.latest.revision: 14
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Remove Duplicate Rows
*Removes the duplicate rows from a dataset*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
##  <a name="Remarks"></a> Module Overview  

This article describes how to use the **Remove Duplicate Rows** module in Azure Machine Learning to remove potential duplicates from a dataset.

To set the criteria for whether a row is duplicate or not, you specify a single column or set of columns to use as **keys**. Two rows are considered duplicates only when the values of all specified features are equal. 

For example, assume your data looks like the following, and represents multiple records for patients. 


| PatID | Initials| Gender|Age|Admitted|
|----|----|----|----|----|
|1|F.M.| M| 53| Jan|
|2| F.A.M.| M| 53| Jan|
|3| F.A.M.| M| 24| Jan|
|3| F.M.| M| 24| Feb|
|4| F.M.| M| 23| Feb|
| | F.M.| M| 23| |
|5| F.A.M.| M| 53| |


Clearly, there are multiple columns that could be used as keys to eliminate duplicates, and your selection might vary depending on your knowledge of the data, and the modeling task for which the data is intended. You might select a single column to use, such as ID, or you might select multiple columns, such as a combination of initials plus age. 

When you run the module, it creates a candidate dataset, and returns a set of rows that have no duplicates across the set of key columns.

## How to use Remove Duplicate Rows

1. Add the module to your experiment. You can find the **Remove Duplicate Rows** module under **Data Transformation**, **Manipulation**.  

2. Connect the dataset that you want to check for duplicate rows.

3. In the **Properties** pane, under **Key column selection filter expression**, click **Launch column selector**, to choose columns to use in identifying duplicates. 

    **Key** does not mean a unique identifier; all columns that you include using hte Column Selector are considered **key columns**. All un-selected columns are considered non-key columns.

    + A missing value is considered a valid value in key columns.

    + The input dataset can have missing values in both key and non-key columns. In key columns, a missing value is considered equal to other missing values, but not equal to non-missing values.  
  
    + In a sparse dataset, the missing value is considered equal only if it equals the default representation of a sparse value.  
  
4. Use the **Retain first duplicate row** checkbox to indicate which row to return when duplicates are found:

    + If selected, the first row is returned and others discarded. 
    + If you uncheck this option, the last duplicate row is kept and and others discarded. 

5. Run the experiment, or click the module and select **Run Selected**.  

6. To review the results, right-click the module, select Results dataset, and click **Visualize**. 

> [!TIP]
> If the results are difficult to understand, or if you want to exclude some columns from consideration, you can remove columns by using the [Select Columns in Dataset](select-columns-in-dataset.md) module.

## Examples  

You can see examples of how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   In the [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726) sample, **Remove Duplicate Rows** is used to consolidate the training and test datasets after adding feature columns  
  
-   The [Movie recommendation](http://go.microsoft.com/fwlink/?LinkId=525276) sample uses **Remove Duplicate Rows** to sanitize the data and ensure that there is only one user rating per movie.  
  
-   In the [Twitter sentiment analysis](http://go.microsoft.com/fwlink/?LinkId=525274) sample, **Remove Duplicate Rows** is applied to only the ID and popularity columns, to ensure that there is only one ranking value per movie.  
  
##  <a name="Notes"></a> Technical Notes  
  
The module works by looping through all rows of the input dataset. It collects into a candidate output dataset all rows where the unique combination of key column values appeared for the first time.  
  
The input dataset is allowed to have missing values in non-key columns and key columns. In key columns, a missing value is considered equal to other missing values, but not equal to non-missing values.  
  
The column array type is preserved independently of the results of row filtering. You cannot force the array to a particular data type by filtering out invalid values; the column array type is based on all values in the column. This restriction also applies when filtering missing values.  
  
The algorithm used for comparing data values is hash-forced.  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Key column selection filter expression|any|ColumnSelection||Choose the key columns to use when searching for duplicates.|  
|Retain first duplicate row|any|Boolean|true|Indicate whether to keep the first row of a set of duplicates and discard others. If False, the last duplicate row encountered is kept.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Filtered dataset|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of the input datasets are null or empty.|  
|[Error 0020](errors/error-0020.md)|An exception occurs if the number of columns in some of the datasets passed to the module is too small.|  
|[Error 0017](errors/error-0017.md)|An exception occurs if one or more specified columns have a type that is unsupported by the current module.|  
  
## See Also  
 [Manipulation](data-transformation-manipulation.md)   
 [A-Z Module List](a-z-module-list.md)