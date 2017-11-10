---
title: "Error 0077 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0077-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0077
**Error 0077**  
  
 Exception occurs when unknown blob file write mode passed.  
  
 This error in Azure Machine Learning occurs if an invalid argument is passed in the specifications for a blob file destination or source.  
  
## Resolution  
 In almost all modules that import or export data to and from Azure blob storage, parameter values controlling the write mode are assigned by using a dropdown list; therefore, it is not possible to pass an invalid value, and this error should not appear. This error will be deprecated in a later release.  
  
|Exception Messages|  
|------------------------|  
|Unsupported blob write mode.|  
|Unsupported blob write mode: {0}.|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)