---
title: "GetArrayLength"
description: "Returns the length of the specified array.  "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# GetArrayLength
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

  Returns the length of the specified array.  
  
 ## Syntax  
  
```SQL   
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
  
  
