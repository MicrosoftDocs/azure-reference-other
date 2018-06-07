---
title: "Error 0056 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 03/16/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0056-d185d1509344
caps.latest.revision: 9
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0056  
 Exception occurs if the columns you selected for an operation violates requirements.  
  
 This error in Azure Machine Learning occurs when you are choosing columns for an operation that requires the column be of a particular data type. 
 
 This error can also happen if the column is the correct data type, but the module you are using requires that the column also be specifically marked as a feature, label, or categorical column.  
  
 For example, the [Convert to Indicator Values](../convert-to-indicator-values.md) module requires that columns be categorical, and will raise this error if you select a feature column or label column.  
  
## Resolution  
  
1.  Review the data type of the columns that are currently selected. 

2. Ascertain whether the selected columns are categorical, label, or feature columns.  
  
3.  Review the help topic for the module in which you made the column selection, to determine if there are specific requirements for data type or column usage.  
  
3.  Use [Edit Metadata](../edit-metadata.md) to change the column type for the duration of this operation. Be sure to change the column type back to its original value, using another instance of [Edit Metadata](../edit-metadata.md), if you need it for downstream operations.  
  
|Exception Messages|  
|------------------------|  
|One or more selected columns were not in an allowed category.|  
|Column with name "{0}" is not in an allowed category.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)