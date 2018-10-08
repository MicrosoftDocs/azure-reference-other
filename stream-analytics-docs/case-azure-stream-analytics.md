---
title: "CASE (Azure Stream Analytics) | Microsoft Docs"
description: "Evaluates a list of conditions and returns one of multiple possible result expressions."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 7c32501d-0e3e-49e8-8c84-61d33830e355
caps.latest.revision: 7
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---

# CASE (Azure Stream Analytics)
  Evaluates a list of conditions and returns one of multiple possible result expressions.  
  
 The CASE expression has two formats:  
  
-   The simple CASE expression compares an expression to a set of simple expressions to determine the result.  
  
-   The searched CASE expression evaluates a set of Boolean expressions to determine the result.  
  
 Both formats require an ELSE argument.  
  
 CASE can be used in any statement or clause that allows a valid expression. For example, you can use CASE in expressions such as SELECT and in clauses such as WHERE and HAVING.  
  
 **Syntax**  
  
 Simple CASE expression:  
  
```SQL
CASE input_expression   
     WHEN when_expression THEN result_expression [ ...n ]   
     ELSE else_result_expression   
END  
  
``` 
  
 Searched CASE expression:  
  
```SQL  
CASE  
     WHEN Boolean_expression THEN result_expression [ ...n ]   
     ELSE else_result_expression  
END  
  
```  
  
  
