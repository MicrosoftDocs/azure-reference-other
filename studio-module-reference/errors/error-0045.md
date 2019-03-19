---
title: "Error 0045 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0045  
 Exception occurs when it is not possible to create a column because of mixed element types in the source.  
  
 This error in Azure Machine Learning is produced when the element types of two datasets being combined are different.  
  
## Resolution  
 Ensure that all values in a given column in both datasets being combined are of the same type (numeric, Boolean, categorical, string, date, etc.).  
  
|Exception Messages|  
|------------------------|  
|Cannot create column with mixed element types.|  
|Cannot create column with id "{0}" of mixed element types:\n\tType of data[{1}, {0}] is {2}\n\tType of data[{3}, {0}] is {4}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
