---
title: "SIGN (Azure Stream Analytics)"
description: "A mathematical function that returns the positive (+1), zero (0), or negative (-1) sign of the specified expression."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# SIGN (Azure Stream Analytics)
  A mathematical function that returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.  
  
 ## Syntax  
  
```SQL   
SIGN (expression)  
```  
  
## Argument  
 **expression**  
  
 Is an **expression** of the exact numeric or approximate numeric data type category.  
  
## Return Type  
 Returns the same type as submitted in **expression**.  
  
## Example  
  
```SQL  
SELECT SIGN(input.x) AS "The SIGN of the variable x"  
FROM input  
```  
  
  
