---
title: "FLOOR (Azure Stream Analytics)"
description: "A mathematical function that returns the largest integer less than or equal to the specified numeric expression. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# FLOOR (Azure Stream Analytics)
  A mathematical function that returns the largest integer less than or equal to the specified numeric expression.  
  
 ## Syntax  
  
```SQL   
FLOOR (expression)  
```  
  
## Argument  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category.  
  
## Return Type  
 Returns the same type as submitted in **expression**.  
  
## Example  
  
```SQL  
SELECT FLOOR(input.x) AS "The FLOOR of the variable x"  
FROM input  
```  
  
  
