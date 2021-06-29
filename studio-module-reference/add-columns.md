---
title: "ML Studio (classic): Add Columns - Azure"
description: Learn how to use the Add Columns module to combine all columns from two datasets to create a single dataset. 
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs 
ms.date: 05/06/2019
---

# Add Columns

*Adds a set of columns from one dataset to another*

Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Add Columns](add-columns.md) module in Machine Learning Studio (classic) to concatenate two datasets. 

You combine all columns from the two datasets that you specify as inputs to create a single dataset. If you need to concatenate more than two datasets, use several instances of **Add Columns**.  
  
When combining two datasets that contain a different number of rows, we recommend using the [Join Data](join-data.md) module, which supports outer joins on a common key column.

## How to configure Add Columns

1. Add the **Add Columns** module to your experiment.  

2. Connect the two datasets that you want to concatenate. If you want to combine more than two datasets, you can chain together several combinations of **Add Columns**.  
  
    -   It is possible to combine two columns that have a different number of rows. The output dataset is padded with missing values for each row in the smaller source column.  
  
    -   You cannot choose individual columns to add. All the columns from each dataset are concatenated when you use **Add Columns**. Therefore, if you want to add only a subset of the columns, use [Select Columns in Dataset](select-columns-in-dataset.md) to create a dataset with the columns you want.  
  
3.  Run the experiment.  

### Results

After the experiment has run:

+ To see the first rows of the new dataset, right-click the output of **Add Columns** and select **Visualize**.
+ To save and name the concatenated dataset, right-click the output and select **Save as Dataset** .  
  
The number of columns in the new dataset equals the sum of the columns of both input datasets.  
  
If there are two columns with the same name in the input datasets, a numeric suffix is added to the name of the column from the dataset used in the right input column. For example, if there are two instances of a column named **TargetOutcome**, the right column would be renamed **TargetOutcome (1)**.  

## Examples  

For examples of how **Add Columns** is used in an experiment, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Customer relationship prediction](https://go.microsoft.com/fwlink/?LinkId=525941): A column that contains labels is combined with a feature dataset.  

- [Breast cancer detection](https://go.microsoft.com/fwlink/?LinkId=525726): Datasets that contain features are cleaned and then combined by using [Add Rows](add-rows.md),  **Add Columns**, and [Join Data](join-data.md).  

## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Left dataset|[Data Table](data-table.md)|Left dataset|  
|Right dataset|[Data Table](data-table.md)|Right dataset|  
  
## Output  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Combined dataset|[Data Table](data-table.md)|Combined dataset|  
  
## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more input datasets is null or empty.|  
|[Error 0017](errors/error-0017.md)|An exception occurs if one or more specified columns has a type that is unsupported by the current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)
