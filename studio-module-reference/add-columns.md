---
title: "Add Columns | Microsoft Docs"
ms.custom: ""
ms.date: 07/06/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5714a225-befd-438a-9bb5-f6fdc50a4efb
caps.latest.revision: 19
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Add Columns
*Adds a set of columns from one dataset to another*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the [Add Columns](add-columns.md) module to concatenate two datasets. You combine all columns from the two datasets that you specify as inputs to create a single dataset. If you need to concatenate more than two datasets, use several instances of **Add Columns**.  
  
> [!TIP]
>  When combining two datasets that contain a different number of rows, use the [Join Data](join-data.md) module, which supports outer joins on a common key column.  
  
## How to Configure Add Columns  
  
1.  Add the **Add Columns** module to your experiment.  
  
2.  Connect the two datasets that you want to concatenate. If you want to combine more than two datasets, you can chain together several combinations of **Add Columns**.  
  
    -   It is possible to combine two columns that have a different number of rows. The output dataset is padded with missing values for each row in the smaller source column.  
  
    -   You cannot choose individual columns to add. All the columns from each dataset are concatenated when you use **Add Columns**. Therefore, if you want to add only a subset of the columns, use [Select Columns in Dataset](select-columns-in-dataset.md) to create a dataset with the columns you want.  
  
3.  Run the experiment.  
  
     You can right-click the output of **Add Columns** and select **View Results** to see the first rows of the new dataset, or you can select **Save as Dataset** to save and name the concatenated dataset.  
  
    -   The number of columns in the new dataset equals the sum of the columns of both input datasets.  
  
    -   If there are two columns with the same name in the input datasets, a numeric suffix is added to the name of the column from the dataset used in the right input column. For example, if there are two instances of a column named **TargetOutcome**, the right column would be renamed **TargetOutcome (1)**.  
  
## Examples  
 For examples of how **Add Columns** is used in an experiment, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   In the [Customer relationship prediction](http://go.microsoft.com/fwlink/?LinkId=525941) sample, a column that contains labels is combined with a feature dataset.  
  
-   In the [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726) sample, datasets that contain features are cleaned and then combined by using [Add Rows](add-rows.md),  **Add Columns**, and [Join Data](join-data.md).  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Left dataset|[Data Table](data-table.md)|Left dataset|  
|Right dataset|[Data Table](data-table.md)|Right dataset|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Combined dataset|[Data Table](data-table.md)|Combined dataset|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](error-0003.md)|An exception occurs if one or more input datasets is null or empty.|  
|[Error 0017](error-0017.md)|An exception occurs if one or more specified columns has a type that is unsupported by the current module.|  
  
## See Also  
 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)