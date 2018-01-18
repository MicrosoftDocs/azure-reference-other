---
title: "FLOOR (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the largest integer less than or equal to the specified numeric expression. "
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: ddee262a-4266-4649-92f5-cb5c4bbad388
caps.latest.revision: 7
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# FLOOR (Azure Stream Analytics)
  A mathematical function that returns the largest integer less than or equal to the specified numeric expression.  
  
 **Syntax**  
  
```  
FLOOR (expression)  
```  
  
## Arguement  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category.  
  
## Return Type  
 Returns the same type as submitted in **expression**.  
  
## Example  
  
```SQL  
SELECT FLOOR(input.x) AS "The FLOOR of the variable x"  
FROM input  
```  
  
  