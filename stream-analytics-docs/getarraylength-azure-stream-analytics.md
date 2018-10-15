---
title: "GetArrayLength (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the length of the specified array.  "
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: e5efa2e4-57fa-49c6-9620-36eef71e74fb
caps.latest.revision: 7
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# GetArrayLength (Azure Stream Analytics)
  Returns the length of the specified array.  
  
 ## Syntax  
  
```  
GetArrayLength ( array_expression )  
```  
  
## Arguments  
 **array_expression**  
  
 Is the array expression to be evaluated as a source array. array_expression can be a column of type Array or result of another function call.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT   
    GetArrayLength(arrayField) AS arrayLength  
FROM input  
  
```  
  
  
