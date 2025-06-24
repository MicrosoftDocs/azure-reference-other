---
title: "ABS"
description: "A mathematical function that returns the absolute (positive) value of the specified numeric expression. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# ABS (Absolute value)

:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

A mathematical function that returns the absolute (positive) value of the specified numeric expression.  
  
 ## Syntax  
  
```SQL  
ABS (expression )  
```  
  
## Argument  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. ABS can be used with bigint or float columns.  
  
## Return Type  
 Returns the same type as expression.  
  
## Example  
  
```SQL
SELECT ABS(input.x) AS "The ABS of the variable x"  
FROM input  
```  
  
  
