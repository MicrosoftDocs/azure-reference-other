---
title: "SQUARE"
description: "A mathematical function that returns the square of the specified float value. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# SQUARE
  A mathematical function that returns the square of the specified float value.  
  
 ## Syntax  
  
```SQL   
SQUARE (float_expression)  
```  
  
## Argument  
 **float_expression**  
  
 Is an expression of type **float** or of a type that can be implicitly converted to **float**.  
  
## Return Type  
 **float**  
  
## Example  
  
```SQL  
SELECT SQUARE(input.x) AS "The SQUARE of the variable x"  
FROM input  
```  
  
  
