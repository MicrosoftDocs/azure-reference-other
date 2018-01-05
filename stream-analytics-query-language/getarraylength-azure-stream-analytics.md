---
title: "GetArrayLength (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: e5efa2e4-57fa-49c6-9620-36eef71e74fb
caps.latest.revision: 7
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# GetArrayLength (Azure Stream Analytics)
  Returns the length of the specified array.  
  
 **Syntax**  
  
```  
GetArrayLength ( array_expression )  
```  
  
## Arguments  
 **array_expression**  
  
 Is the array expression to be evaluated as a source array. array_expression can be a column of type Array or result of another function call.  
  
## Return Types  
 bigint  
  
## Examples  
  
```  
SELECT   
    GetArrayLength(arrayField) AS arrayLength  
FROM input  
  
```  
  
  