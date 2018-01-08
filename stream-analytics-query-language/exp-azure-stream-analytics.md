---
title: "EXP (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 92f18405-2036-4922-a74d-2c9dab926245
caps.latest.revision: 8
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# EXP (Azure Stream Analytics)
  A mathematical function that returns the exponential value of the specified **float** expression.  
  
 Syntax  
  
```  
EXP (float_expression)  
```  
  
## Arguement  
 **float_expression**  
  
 Is an expression of type **float** or of a type that can be implicitly converted to **float**.  
  
## Return Type  
 **float**  
  
## Example  
  
```  
SELECT EXP(input.x) AS "The EXP of the variable x"  
FROM input  
```  
  
  