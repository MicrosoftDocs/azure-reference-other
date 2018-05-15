---
title: "Error 0140 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 08/16/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0140-d185d1509344
caps.latest.revision: 5
author: rastala
ms.author: roastala
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