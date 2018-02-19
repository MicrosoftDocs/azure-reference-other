---
title: "Data Transformation - Manipulation | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 92b32033-f75f-4854-ac8f-9110b3fe7e09
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Data Transformation - Manipulation

This article describes the modules in Azure Machine Learning Studio that are provided for basic data manipulation.  While Studio supports other tasks that are very specific to machine learning, such as normalization or feature selection, the modules in this group are intended for more general tasks. 

> [!TIP]
> You can now use Azure Machine Learning Workbench to perform more sophisticated data cleanup and preparations tasks, using "learn by example" functions. See [this blog](https://blogs.technet.microsoft.com/machinelearning/2017/09/25/by-example-transformations-in-the-azure-machine-learning-workbench/) from the Machine Learning team for examples.
   
## Data manipulation tasks
 
The modules in this group are intended to support core data management tasks that might need to be performed in Studio, such as:  
  
-   Combining two datasets, either by using joins, or by merging columns or rows
  
-   Creating new categories to use in grouping data  
  
-   Modifying column headings, changing column data types, or flagging columns as features or labels  
  
-   Checking for missing values and replacing them with appropriate values   
  
### Related tasks

+ To perform sampling or divide a dataset into trainign and testing sets, see [Sample and Split](data-transformation-sample-and-split.md).

+ To scale numbers, normalize data, or put numerical values into bins, use the modules in [Scale and Reduce](data-transformation-scale-and-reduce.md).  
  
+ To perform calculations on numeric data fields or generate commonly used statistics, use the tools in [Statistical Functions](statistical-functions.md).  
  
## Examples  

For examples of how to work with complex data in machine learning experiments, see these samples in the [Azure AI Gallery](http://azure.microsoft.com/documentation/services/machine-learning/models/):  

- [Data Processing and Analysis](http://go.microsoft.com/fwlink/?LinkId=525733): Demonstrates key tools and processes.

- [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726): Illustrates how to partition datasets and apply special processing to each partition.  
 
##  Modules in this category

The **Data Transformation/Manipulation** category includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Add Columns](add-columns.md)|Adds a set of columns from one dataset to another|  
|[Add Rows](add-rows.md)|Appends a set of rows from an input dataset to the end of another dataset|  
|[Apply SQL Transformation](apply-sql-transformation.md)|Runs a SQLite query on input datasets to transform the data|  
|[Clean Missing Data](clean-missing-data.md)|Specifies how to handle the values missing from a dataset<br /><br /> This module replaces [Missing Values Scrubber (deprecated)](missing-values-scrubber-deprecated.md), which has been deprecated.|  
|[Convert to Indicator Values](convert-to-indicator-values.md)|Converts categorical values in columns to indicator values|  
|[Edit Metadata](edit-metadata.md)|Edits metadata associated with columns in a dataset|  
|[Group Categorical Values](group-categorical-values.md)|Groups data from multiple categories into a new category|  
|[Join Data](join-data.md)|Joins two datasets|  
|[Remove Duplicate Rows](remove-duplicate-rows.md)|Removes the duplicate rows from a dataset|  
|[Select Columns in Dataset](select-columns-in-dataset.md)|Selects columns to include or exclude from a dataset in an operation|  
|[Select Columns Transform](select-columns-transform.md)|Creates a transformation that selects the same subset of column as in the given dataset|  
|[SMOTE](smote.md)|Increases the number of low incidence examples in a dataset using synthetic minority oversampling|  
  
## See also  
 [Data Transformation](data-transformation.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [A-Z Module List](a-z-module-list.md)