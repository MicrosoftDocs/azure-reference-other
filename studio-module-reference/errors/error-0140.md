---
title: "Error 0140 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 08/16/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0140  
 Exception occurs if passed column set argument does not contain other columns except label column.  
  
 This error occurs if you connected a dataset to a module that requires multiple columns, including features, but you have provided only the label column.  
  
## Resolution  
 Choose at least one feature column to include in the dataset.  
  
|Exception Messages|  
|------------------------|  
|Specified column set does not contain other columns except label column.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
