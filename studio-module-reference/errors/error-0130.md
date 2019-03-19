---
title: "Error 0130 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0130  
 Exception occurs when all rows in the training dataset contain missing values.  
  
 This occurs when some column in the training dataset is empty.  
  
## Resolution  
 Use the [Clean Missing Data](../clean-missing-data.md) module to remove columns with all missing values.  
  
|Exception Messages|  
|------------------------|  
|All rows in training dataset contain missing values.  Consider using the Clean Missing Data module to remove missing values.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
