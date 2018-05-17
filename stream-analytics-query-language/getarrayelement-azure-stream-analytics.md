---
title: GetArrayElement (Azure Stream Analytics) | Microsoft Docs
description: Returns the array element at the specified index. Useful for parsing arrays and nested objects in JSON and AVRO formatted input event data.
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 21dd9ec1-6722-4175-98db-c4e5e2f7cd6d
caps.latest.revision: 7
ms.workload: data-services
ms.date: 05/17/2018
---

# GetArrayElement (Azure Stream Analytics)
Returns the array element at the specified index. This function is useful for parsing arrays and nested objects in JSON and AVRO formatted input event data. For more examples, see [Complex Data Types](complex-data-types-stream-analytics.md). If you need to return all nested elements in an array, use [GetArrayElements](getarrayelements-azure-stream-analytics.md) instead.
  
 **Syntax**  
  
```  
GetArrayElement ( array_expression, bigint_expression )  
```  
  
## Arguments  
 **array_expression**  
  
 Is the array expression to be evaluated as a source array. array_expression can be a column of type Array or result of another function call.  
  
 **bigint_expression**  
  
 Is the bigint expression to be evaluated as array index. The ordinal position in the array of elements, starting at 0.
  
### Return Types  
 Return type is determined by the array element type and can be any of the [supported types.](data-types-azure-stream-analytics.md)  
  
### Examples  
  
```SQL  
SELECT   
    GetArrayElement(arrayField, 0) AS firstElement  
FROM input  
  
```  
  
 ## See also
- [GetArrayElements](getarrayelements-azure-stream-analytics.md)
- [Complex Data Types](complex-data-types-stream-analytics.md)
- [CROSS APPLY](apply-azure-stream-analytics.md)

