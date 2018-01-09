---
title: "FLOOR (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: ddee262a-4266-4649-92f5-cb5c4bbad388
caps.latest.revision: 7
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
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
  
  