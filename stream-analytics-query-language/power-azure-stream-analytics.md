---
title: "POWER (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 89a126bc-f801-4697-b1dd-93235d1f54a0
caps.latest.revision: 8
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# POWER (Azure Stream Analytics)
  A mathematical function that returns the value of the specified expression to the specified power.  
  
 **Syntax**  
  
```  
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
  
  