---
title: "SQRT (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 3a850384-fbee-4377-8423-ce5547e46b46
caps.latest.revision: 10
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
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
  
  