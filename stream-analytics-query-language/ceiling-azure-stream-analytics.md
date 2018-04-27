---
title: "CEILING (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the smallest integer greater than or equal to the specified numeric expression."
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 86b82a0b-cb22-40fa-a5b3-3731e2dde085
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: jasonh
---

# CEILING (Azure Stream Analytics)
  A mathematical function that returns the smallest integer greater than or equal to the specified numeric expression.  
  
 **Syntax**  
  
```  
CEILING (expression)  
```  
  
## Arguement  
 **expression**  
  
 An expression of the exact numeric or approximate numeric data type category.  
  
### Return Types  
 Returns the same type as submitted in the expression.  
  
### Example  
  
```SQL 
SELECT CEILING(input.x) AS "The CEILING of the variable x"  
FROM input  
```  
  
  
