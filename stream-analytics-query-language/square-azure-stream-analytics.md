---
title: "SQUARE (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the square of the specified float value. "
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: be6fb339-a9bd-4d7d-b7e3-3c0a0890d5c5
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---

# SQUARE (Azure Stream Analytics)
  A mathematical function that returns the square of the specified float value.  
  
 **Syntax**  
  
```  
SQUARE (float_expression)  
```  
  
## Arguement  
 **float_expression**  
  
 Is an expression of type **float** or of a type that can be implicitly converted to **float**.  
  
## Return Type  
 **float**  
  
## Example  
  
```SQL  
SELECT SQUARE(input.x) AS "The SQUARE of the variable x"  
FROM input  
```  
  
  