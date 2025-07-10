---
title: "POWER"
description: "A mathematical function that returns the value of the specified expression to the specified power. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# POWER
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

  A mathematical function that returns the value of the specified expression to the specified power.  
  
 ## Syntax  
  
```SQL   
POWER (float_expression, y)  
```  
  
## Arguments  
 **float_expression**  
  
 Is an expression of type **float** or of a type that can be implicitly converted to a **float**.  
  
 **y**  
  
 The power to which to raise **float_expression**. **y** can be an expression of the exact numeric or approximate numeric data type category.  
  
## Return Type  
 Returns the same type as submitted in **float_expression**. For example, if a bigint was submitted as **float_expressions**, the result returned is bigint.  
  
## Example  
  
```SQL  
SELECT POWER(input.x, 3) AS "The 3rd POWER of the variable x"  
FROM input  
```  
  
  
