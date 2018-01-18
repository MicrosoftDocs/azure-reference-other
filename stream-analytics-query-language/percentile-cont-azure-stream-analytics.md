---
title: "Percentile_Cont (Azure Stream Analytics) | Microsoft Docs"
description: "Calculates a percentile based on a continuous distribution of the entire data set."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 7f4d2984-d4bc-4560-abd9-2d20cfe9104c
caps.latest.revision: 2
ms.workload: data-services
ms.date: 09/08/2016
ms.author: sngun
---
# Percentile_Cont (Azure Stream Analytics)
Calculates a percentile based on a continuous distribution of the entire data set. The result is interpolated and might not be equal to any of the specific values from the input set. 
  
 **Syntax**  
  
``` 
PERCENTILE_CONT ( numeric_literal )
      OVER ( ORDER BY order_by_expression [ ASC | DESC ] )
```  
  
## Arguments  
 **numeric_literal**  
  
The percentile to compute. The value must range between 0 and 1.  

 **OVER ( ORDER BY order_by_expression [ ASC | DESC] )**

Specifies a list of numeric values to sort and compute the percentile over. Only one order_by_expression is allowed. The expression must evaluate to a numeric type. Other data types are not allowed. The default sort order is ascending.

## Return Types  

Float 
  
## Examples  

The following example uses PERCENTILE_CONT to find the 95th percentile of service availability across regions. Note that the function may not return a percentile that is within the input data set. This is because PERCENTILE_CONT interpolates the appropriate value, whether or not it exists in the data set.
  
```SQL  
SELECT PERCENTILE_CONT(0.95) OVER (ORDER BY serviceAvailability)
FROM testInput
GROUP BY SlidingWindow(hours, 1)
```  
  
 **Example input:**
| Regions | ServiceAvailability |
|---|---|
| A |	0.98 |
| B |	0.93 |
| C |	0.78 |
| D |	0.99 |
| E |	0.89 |

 **Example output:**

0.988
