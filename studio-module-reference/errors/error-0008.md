---
title: "Error 0008 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0008-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0008  
 Exception occurs if parameter is not in range.  
  
 You will receive this error in Azure Machine Learning if the parameter in the message is outside the bounds required for the module to process the data.  
  
 For example, this error is displayed if you try to use [Add Rows](../add-rows.md) to combine two datasets that have a different number of columns.  
  
## Resolution  
 Revisit the module throwing the exception and modify the parameter to be within the specified range.  
  
|Exception Messages|  
|------------------------|  
|Parameter value is not in the specified range.|  
|Parameter "{0}" value is not in range.|  
|Parameter "{0}" value should be in the range of [{1}, {2}].|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)