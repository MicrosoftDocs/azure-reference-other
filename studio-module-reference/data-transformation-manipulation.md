---
title: "Data Transformation - Manipulation | Microsoft Docs"
description: "Learn about the Azure Machine Learning Studio modules that you can use for basic data manipulation."
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 92b32033-f75f-4854-ac8f-9110b3fe7e09
caps.latest.revision: 17
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Data Transformation - Manipulation

This article describes the modules in Azure Machine Learning Studio that you can use for basic data manipulation.

Machine Learning Studio supports tasks that are specific to machine learning, such as normalization or feature selection. The modules in this category are intended for more general tasks.

> [!TIP]
> You can use Azure Machine Learning Workbench to perform more sophisticated data cleanup and preparations tasks by using "learn by example" functions. For examples, see Microsoft Machine Learning team blog post [Data transformations “by example” in Machine Learning Workbench](https://blogs.technet.microsoft.com/machinelearning/2017/09/25/by-example-transformations-in-the-azure-machine-learning-workbench/).
   
## Data manipulation tasks
 
The modules in this category are intended to support core data management tasks that might need to be performed in Machine Learning Studio. The following tasks are examples of core data management tasks:
-   Combine two datasets, either by using joins, or by merging columns or rows.
-   Create new categories to use in grouping data.
-   Modify column headings, change column data types, or flag columns as features or labels.
-   Check for missing values, and then replace them with appropriate values.
  
## Related tasks

- Perform sampling or divide a dataset into training and testing sets: Use the [Data Transformation - Sample and Split](data-transformation-sample-and-split.md) modules.
- Scale numbers, normalize data, or put numerical values into bins: Use the [Data Transformation - Scale and Reduce](data-transformation-scale-and-reduce.md) modules.
- Perform calculations on numeric data fields or to generate commonly used statistics: Use the tools in [Statistical Functions](statistical-functions.md).
  
## Examples

For examples of how to work with complex data in machine learning experiments, see these samples in the [Azure AI Gallery](http://azure.microsoft.com/documentation/services/machine-learning/models/):
- [Data Processing and Analysis](http://go.microsoft.com/fwlink/?LinkId=525733): Demonstrates key tools and processes.
- [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726): Illustrates how to partition datasets, and then apply special processing to each partition.
 
##  Modules in this category

The **Data Transformation - Manipulation** category includes the following modules:
  
- [Add Columns](add-columns.md): Adds a set of columns from one dataset to another.
- [Add Rows](add-rows.md): Appends a set of rows from an input dataset to the end of another dataset.
- [Apply SQL Transformation](apply-sql-transformation.md): Runs a SQLite query on input datasets to transform the data.
- [Clean Missing Data](clean-missing-data.md): Specifies how to handle values that are missing from a dataset. This module replaces [Missing Values Scrubber (deprecated)](missing-values-scrubber-deprecated.md), which has been deprecated.
- [Convert to Indicator Values](convert-to-indicator-values.md): Converts categorical values in columns to indicator values.
- [Edit Metadata](edit-metadata.md): Edits metadata that's associated with columns in a dataset.
- [Group Categorical Values](group-categorical-values.md): Groups data from multiple categories into a new category.
- [Join Data](join-data.md): Joins two datasets.
- [Remove Duplicate Rows](remove-duplicate-rows.md): Removes duplicate rows from a dataset.
- [Select Columns in Dataset](select-columns-in-dataset.md): Selects columns to include in a dataset or exclude from a dataset in an operation.
- [Select Columns Transform](select-columns-transform.md): Creates a transformation that selects the same subset of columns as in a specified dataset.
- [SMOTE](smote.md): Increases the number of low-incidence examples in a dataset by using synthetic minority oversampling.
  
## See also

- [Data Transformation](data-transformation.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)
- [A-Z module list](a-z-module-list.md)