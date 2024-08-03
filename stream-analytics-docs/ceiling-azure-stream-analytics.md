---
title: "CEILING (Azure Stream Analytics)"
description: "A mathematical function that returns the smallest integer greater than or equal to the specified numeric expression."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# CEILING (Azure Stream Analytics)
  A mathematical function that returns the smallest integer greater than or equal to the specified numeric expression.  
  
 ## Syntax  
  
```SQL   
CEILING (expression)  
```  
  
## Argument  
 **expression**  
  
 An expression of the exact numeric or approximate numeric data type category.  
  
### Return Types  
 Returns the same type as submitted in the expression.  
  
### Example  
  
```SQL 
SELECT CEILING(input.x) AS "The CEILING of the variable x"  
FROM input  
```  
  
  
