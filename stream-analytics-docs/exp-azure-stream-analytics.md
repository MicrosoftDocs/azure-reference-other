---
title: "EXP (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the exponential value of the specified  expression. "
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 92f18405-2036-4922-a74d-2c9dab926245
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
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
  
  
