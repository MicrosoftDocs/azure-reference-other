---
title: "Collect (Azure Stream Analytics) | Microsoft Docs"
description: "Returns an array with all record values from the window. "
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea


ms.service: stream-analytics
ms.topic: reference
ms.assetid: 4ecadc16-b061-45ff-935f-3d03996a53f5
caps.latest.revision: 7
ms.workload: data-services
ms.date: 05/24/2016
ms.author: mamccrea
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
Collect takes optional scalar expression which allows to specify projection over the collected events. Without parameter it collects full event records.
  
## Return Types  
Array of values projected by the `<scalar_expression>` parameter, or array of record values if no parameter provided.  

## General Remarks
Ordering of the values within returned array is **not** guaranteed

## Examples

Collect all input events within 10 second window.

```SQL  
SELECT Collect() AS allEvents 
FROM Input 
GROUP BY Tumbling(second, 10) 
```

Collect sums of `a` and `b` fields of the input events within 10 second window.

```SQL  
SELECT Collect(a + b) AS allab 
FROM Input 
GROUP BY Tumbling(second,10) 
```
