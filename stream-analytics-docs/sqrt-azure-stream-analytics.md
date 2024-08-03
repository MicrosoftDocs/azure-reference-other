---
title: "SQRT (Azure Stream Analytics)"
description: "A mathematical function that returns the square root of the specified float value."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# SQRT (Azure Stream Analytics)
  A mathematical function that returns the square root of the specified float value.  
  
 ## Syntax  
  
```SQL   
SQRT (float_expression)  
```  
  
## Argument  
 float_expression  
  
 Is an expression of type float or of a type that can be implicitly converted to float. The value must be non-negative.  
  
## Return Type  
 **float**  
  
## Example  
  
```SQL  
SELECT SQRT(input.x) AS "The SQRT of the variable x"  
FROM input  
```  
  
  
