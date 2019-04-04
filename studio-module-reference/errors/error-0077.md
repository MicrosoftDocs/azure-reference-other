---
title: "Error 0077 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0077  
 Exception occurs when unknown blob file write mode passed.  
  
 This error in Azure Machine Learning occurs if an invalid argument is passed in the specifications for a blob file destination or source.  
  
**Resolution :**
 In almost all modules that import or export data to and from Azure blob storage, parameter values controlling the write mode are assigned by using a dropdown list; therefore, it is not possible to pass an invalid value, and this error should not appear. This error will be deprecated in a later release.  
  
|Exception Messages|  
|------------------------|  
|Unsupported blob write mode.|  
|Unsupported blob write mode: {0}.|  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
