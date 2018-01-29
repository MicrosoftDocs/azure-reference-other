---
title: "ABS (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the absolute (positive) value of the specified numeric expression. "
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 88f0e7d4-dc2e-4c0b-a9b5-6942a85f93a9
caps.latest.revision: 9
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---

# ABS (Absolute value- Azure Stream Analytics)
  A mathematical function that returns the absolute (positive) value of the specified numeric expression.  
  
 **Syntax**  
  
```  
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
  
  