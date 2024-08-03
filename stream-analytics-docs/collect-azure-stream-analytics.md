---
title: "Collect (Azure Stream Analytics)"
description: "Returns an array with all record values from the window. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# Collect (Azure Stream Analytics)
Returns an array with all record values from the window.

 
 ## Syntax  
  
```SQL
-- Aggregate Function Syntax
Collect ( [ <scalar_expression> ] )

-- Analytic Function Syntax
Collect ( [ <scalar_expression> ] ) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
```  
  
## Arguments
Collect takes an optional scalar expression that allows you to specify a projection over the collected events. Without the parameter, full event records are collected.
  
## Return Types  
Array of values projected by the `<scalar_expression>` parameter, or array of record values if no parameter is provided.  

## General Remarks
Ordering of the values within returned array is **not** guaranteed

## Examples

Collect all input events within a 10 second window.

```SQL  
SELECT Collect() AS allEvents 
FROM Input 
GROUP BY Tumbling(second, 10) 
```

Collect the sums of the `a` and `b` fields of the input events within a 10 second window.

```SQL  
SELECT Collect(a + b) AS allab 
FROM Input 
GROUP BY Tumbling(second,10) 
```
