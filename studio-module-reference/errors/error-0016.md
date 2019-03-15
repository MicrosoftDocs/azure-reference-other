---
title: "Error 0016 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0016  
 Exception occurs if input datasets passed to the module should have compatible column types but do not.  
  
 You will receive this error in Azure Machine Learning if the types of the columns passed in two or more datasets are not compatible with each other.  
  
## Resolution  
 Use [Edit Metadata](../edit-metadata.md), modify the original input dataset, or use [Convert to Dataset](../convert-to-dataset.md) to ensure that the types of the columns are compatible.  
  
|Exception Messages|  
|------------------------|  
|Columns with corresponding index in input datasets do have incompatible types.|  
|Columns {0} and {1} are incompatible.|  
|Column element types are not compatible for column {0} (zero-based) of input datasets ({1} and {2} respectively).|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
