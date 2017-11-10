---
title: "Error 0139 | Microsoft Docs"
ms.custom: ""
ms.date: 06/14/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0139-d185d1509344
caps.latest.revision: 10
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0139
**Error 0139**  
  
 Exception occurs when it is not possible to convert a column to another type.  
  
 This error in Azure Machine Learning occurs when you try to convert a column to a different data type, but that type is not supported by the current operation or by the module.  
  
 The error might also appear when a module tries to implicitly convert data to meet requirements of the current module, but the conversion is not possible.  
  
## Resolution  

1. Review your input data and determine the exact data type of the column that you want to use, and the data type of the column that is producing the error. Sometimes you might think the data type is correct, but find that an upstream operation has modified the data type or usage of a column. Use the [Edit Metadata](../edit-metadata.md) module to reset column metadata to its original state. 
2. Look at the module help page to verify the requirements for the specified operation. Determine which data types are supported by the current module, and what range of values is supported. 
3. If values need to be truncated, rounded, or outliers removed, use the [Apply Math Operation](../apply-math-operation.md) or [Clip Values](../clip-values.md) modules to make corrections.
4. Consider whether it is possible to convert or cast the column to a different data type. The following modules all provide considerable flexibility and power for modifying data: 
  
   + [Apply SQL Transformation](../apply-sql-transformation.md)
   + [Execute R Script](../execute-r-script.md)
   + [Execute Python Script](../execute-python-script.md).  

> [!NOTE]
> Still not working? Consider providing additional feedback on the problem, to help us develop better troubleshooting guidance. Just submit feedback on this page and provide the name of the module that generated the error, and the data type conversion that failed.
  
|Exception Messages|  
|------------------------|  
|Not allowed conversion.|  
|Could not convert: {0}.|  
|Could not convert: {0}, on row {1}.|  
|Could not convert column of type {0} to column of type {1} on row {2}.|  
|Could not convert column "{2}" of type {0} to column of type {1} on row {3}.|  
|Could not convert column "{2}" of type {0} to column "{3}" of type {1} on row {4}.|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)