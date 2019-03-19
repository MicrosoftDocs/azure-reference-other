---
title: "Error 0060 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0060  
 Exception occurs when an out of range column range is specified in a column picker.  
  
 This error in Azure Machine Learning occurs when an out-of-range column range is specified in the Column Selector. You will receive this error if the column range in the column picker does not correspond to the columns in the dataset.  
  
## Resolution  
 Modify the column range in the column picker to correspond to the columns in the dataset.  
  
|Exception Messages|  
|------------------------|  
|Invalid or out of range column index range specified.|  
|Column range "{0}" is invalid or out of range.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
