---
title: "Error 0037 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0037-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0037  
 Exception occurs if multiple label columns are specified and just one is allowed.  
  
 This error in Azure Machine Learning occurs if more than one column is selected to be the new label column. Most supervised learning algorithms require a single column to be marked as the target or label.  
  
## Resolution  
 Make sure to select a single column as the new label column.  
  
|Exception Messages|  
|------------------------|  
|Multiple label columns are specified.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)