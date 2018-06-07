---
title: "Error 0080 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0080-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0080  
 Exception occurs when column with all values missing is not allowed by module.  
  
 This error in Azure Machine Learning is produced when one or more of the columns consumed by the module contains all missing values. For example, if a module is computing aggregate statistics for each column, it cannot operate on a column containing no data. In such cases, module execution is halted with this exception.  
  
## Resolution  
 Revisit the input dataset and remove any columns that contain all missing values.  
  
|Exception Messages|  
|------------------------|  
|Columns with all values missing are not allowed.|  
|Column {0} has all values missing.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)