---
title: "Error 0141 | Microsoft Docs"
ms.custom: ""
ms.date: 08/16/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0141-d185d1509344
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0141
**Error 0141**  
  
 Exception occurs if the number of the selected numerical columns and unique values in the categorical and string columns is too small.  
  
 This error in Azure Machine Learning occurs when there are not enough unique values in the selected column to perform the operation.  
  
## Resolution  
 Some operations perform statistical operations on feature and categorical columns, and if there are not enough values, the operation might fail or return an invalid result. Check your dataset to see how many values there are in the fature and label columns, and determine whether the operation you are trying to perform is statistically valid.  
  
 If the source dataset is valid, you might also check whether some upstream data maniipulation or metadata operation has changed the data and removed some values.  
  
 If upstream operations include splitting, sampling, or resampling, verify that the outputs contain the expected number of rows and values.  
  
|Exception Messages|  
|------------------------|  
|The number of the selected numerical columns and unique values in the categorical and string columns is too small.|  
|The total number of the selected numerical columns and unique values in the categorical and string columns (currently {0}) should be at least {1}|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)