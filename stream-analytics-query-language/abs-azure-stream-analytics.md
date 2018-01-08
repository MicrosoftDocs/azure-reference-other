---
title: "ABS (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 88f0e7d4-dc2e-4c0b-a9b5-6942a85f93a9
caps.latest.revision: 9
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# ABS (Azure Stream Analytics)
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
  
```  
SELECT ABS(input.x) AS "The ABS of the variable x"  
FROM input  
```  
  
  