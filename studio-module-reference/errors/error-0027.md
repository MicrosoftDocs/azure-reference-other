---
title: "Error 0027 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0027-d185d1509344
caps.latest.revision: 8
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0027  
 Exception occurs in case when two objects have to be of the same size but are not.  
  
 This is an extremely common error in Azure Machine Learning and can be caused by many conditions.  
  
## Resolution  
 There is no specific resolution. However, you can check for conditions such as  the following:  
  
-   If you are renaming columns, make sure that each list (the input columns and the list of new names) has the same number of items.  
  
-   If you are joining or concatenating two datasets, make sure they have the same schema.  
  
-   If you are joining two datsets that have multiple columns, make sure that the key columns have the same data type, and select the option **Allow duplicates and preserve column order in selection**.  
  
|Exception Messages|  
|------------------------|  
|The size of passed objects is inconsistent.|  
|The size of "{0}" is inconsistent with size of "{1}".|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)