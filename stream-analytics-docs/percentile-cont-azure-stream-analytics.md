---
title: "Percentile_Cont"
description: "Calculates a percentile based on a continuous distribution of the entire data set."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# Percentile_Cont
Calculates a percentile based on a continuous distribution of the entire data set. The result is interpolated and might not be equal to any of the specific values from the input set. 
  
 ## Syntax  
  
```SQL  
PERCENTILE_CONT ( numeric_literal )
      OVER ( ORDER BY order_by_expression [ ASC | DESC ] )
```  
  
## Arguments  
 **numeric_literal**  
  
The percentile to compute. The value must range between 0 and 1.  

 **OVER ( ORDER BY order_by_expression [ ASC | DESC] )**

Specifies a list of numeric values to sort and compute the percentile over. Only one order_by_expression is allowed. The expression must be of BIGINT or FLOAT. The default sort order is ascending.

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
|---------|---------|
| A |	0.98 |
| B |	0.93 |
| C |	0.78 |
| D |	0.99 |
| E |	0.89 |

 **Example output:**

0.988
