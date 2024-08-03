---
title: "EXP (Azure Stream Analytics)"
description: "A mathematical function that returns the exponential value of the specified  expression. "
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# EXP (Azure Stream Analytics)
  A mathematical function that returns the exponential value of the specified **float** expression.  
  
 Syntax  
  
```SQL   
EXP (float_expression)  
```  
  
## Argument  
 **float_expression**  
  
 Is an expression of type **float** or of a type that can be implicitly converted to **float**.  
  
## Return Type  
 **float**  
  
## Example  
  
```SQL  
SELECT EXP(input.x) AS "The EXP of the variable x"  
FROM input  
```  
  
  
