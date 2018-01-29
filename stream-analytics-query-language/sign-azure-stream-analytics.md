---
title: "SIGN (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the positive (+1), zero (0), or negative (-1) sign of the specified expression."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: dbac5267-6bc2-42c9-98f8-5b05485b54b7
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# SIGN (Azure Stream Analytics)
  A mathematical function that returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.  
  
 **Syntax**  
  
```  
SIGN (expression)  
```  
  
## Arguement  
 **expression**  
  
 Is an **expression** of the exact numeric or approximate numeric data type category.  
  
## Return Type  
 Returns the same type as submitted in **expression**.  
  
## Example  
  
```SQL  
SELECT SIGN(input.x) AS "The SIGN of the variable x"  
FROM input  
```  
  
  