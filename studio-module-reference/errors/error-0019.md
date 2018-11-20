---
title: "Error 0019 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0019-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0019  
 Exception occurs if column is expected to contain sorted values, but it does not.  
  
 You will receive this error in Azure Machine Learning if the specified column values are out of order.  
  
## Resolution  
 Sort the column values by manually modifying the input dataset and rerun the module.  
  
|Exception Messages|  
|------------------------|  
|Values in column are not sorted.|  
|Values in column "{0}" are not sorted.|  
|Values in column "{0}" of dataset "{1}" are not sorted.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)