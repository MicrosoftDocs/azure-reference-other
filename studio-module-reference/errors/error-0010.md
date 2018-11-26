---
title: "Error 0010 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0010-d185d1509344
caps.latest.revision: 6
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0010  
 Exception occurs if input datasets have column names that should match but do not.  
  
 You will receive this error in Azure Machine Learning if the column index in the message has different column names in the two input datasets.  
  
## Resolution  
 Use [Edit Metadata](../edit-metadata.md) or modify the original dataset to have the same column name for the specified column index.  
  
|Exception Messages|  
|------------------------|  
|Columns with corresponding index in input datasets have different names.|  
|Column names are not the same for column {0} (zero-based) of input datasets ({1} and {2} respectively).|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)