---
title: "GetArrayElement (Azure Stream Analytics) | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 21dd9ec1-6722-4175-98db-c4e5e2f7cd6d
caps.latest.revision: 7
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# GetArrayElement (Azure Stream Analytics)
  Returns the array element at the specified index.  
  
 **Syntax**  
  
```  
GetArrayElement ( array_expression, bigint_expression )  
```  
  
## Arguments  
 **array_expression**  
  
 Is the array expression to be evaluated as a source array. array_expression can be a column of type Array or result of another function call.  
  
 **bigint_expression**  
  
 Is the bigint expression to be evaluated as array index  
  
### Return Types  
 Return type is determined by the array element type and can be any of the [supported types.](data-types-azure-stream-analytics.md)  
  
### Examples  
  
```SQL  
SELECT   
    GetArrayElement(arrayField, 0) AS firstElement  
FROM input  
  
```  
  
  