---
title: "SIGN (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: dbac5267-6bc2-42c9-98f8-5b05485b54b7
caps.latest.revision: 8
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
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
  
```  
SELECT SIGN(input.x) AS "The SIGN of the variable x"  
FROM input  
```  
  
  