---
title: "Error 0028 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0028-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0028  
 Exception occurs in the case when column set contains duplicated column names and it is not allowed.  
  
 This error in Azure Machine Learning occurs when column names are duplicated; that is, not unique.  
  
## Resolution  
 If any columns have same name, add an instance of [Edit Metadata](../edit-metadata.md) between the input dataset and the module raising the error. Use the Column Selector in [Edit Metadata](../edit-metadata.md) to select columns to rename, and type the new columns names into the **New column names** textbox. If you are renaming multiple columns, ensure that the values you type in the **New column names** are unique.  
  
|Exception Messages|  
|------------------------|  
|Column set contains duplicated column name(s).|  
|The name "{0}" is duplicated.|  
|The name "{0}" is duplicated in "{1}".|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)