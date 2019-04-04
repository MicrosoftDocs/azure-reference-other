---
title: "Error 0017 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 06/14/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0017  
 Exception occurs if a selected column uses a data type that is not supported by the current module.  
  
 For example, you might receive this error in Azure Machine Learning if your column selection includes a column with a data type that cannot be processed by the module, such as a string column for a math operation, or a score column where a categorical feature column is required.  
  
**Resolution :**
 1. Identify the column that is the problem.
 2. Review the requirements of the module.
 3. Modify the column to make it conform to requirements. You might need to use several of the following modules to make changes, depending on the column and the conversion you are attempting:
    + Use [Edit Metadata](../edit-metadata.md) to change the data type of columns, or to change the column usage from feature to numeric, categorical to non-categorical and so forth.
    + Use [Convert to Dataset](../convert-to-dataset.md) to ensure that all included columns use data types that are supported by Azure Machine Learning.  If you cannot convert the columns, consider removing them from the input dataset.
    + Use the [Apply SQL Transformation](../apply-sql-transformation.md) or [Execute R Script](../execute-r-script.md) modules to cast or convert any columns that cannot be modified using [Edit Metadata](../edit-metadata.md). These modules provide more flexibility for working with datetime data types.
    + For numeric data types, you can use the [Apply Math Operation](../apply-math-operation.md) module to round or truncate values, or use the [Clip Values](../clip-values.md) module to remove out of range values.  
 4. As a last resort, you might need to modify the original input dataset.

> [!TIP]
> Unable to find a resolution that matches your scenario? You can provide feedback on this topic that includes the name of the module that generated the error, and the data type and cardinality of the column. We will use the information to provide more targeted troubleshooting steps for common scenarios. 
  
|Exception Messages|  
|------------------------|  
|Cannot process column of current type. The type is not supported by the module.|  
|Cannot process column of type {0}. The type is not supported by the module.|  
|Cannot process column "{1}" of type {0}. The type is not supported by the module.|  
|Cannot process column "{1}" of type {0}. The type is not supported by the module. Parameter name: {2}|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
