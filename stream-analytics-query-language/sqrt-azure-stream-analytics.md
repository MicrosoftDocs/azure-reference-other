---
title: "SQRT (Azure Stream Analytics) | Microsoft Docs"
description: "A mathematical function that returns the square root of the specified float value."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 3a850384-fbee-4377-8423-ce5547e46b46
caps.latest.revision: 10
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---

# SQRT (Azure Stream Analytics)
  A mathematical function that returns the square root of the specified float value.  
  
 **Syntax**  
  
```  
SQRT (float_expression)  
```  
  
## Argument  
 float_expression  
  
 Is an expression of type float or of a type that can be implicitly converted to float. The value must be non-negative.  
  
## Return Type  
 **float**  
  
## Example  
  
```SQL  
SELECT SQRT(input.x) AS "The SQRT of the variable x"  
FROM input  
```  
  
  