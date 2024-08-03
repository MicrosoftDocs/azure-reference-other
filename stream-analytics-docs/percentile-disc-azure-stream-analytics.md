---
title: "Percentile_Disc (Azure Stream Analytics)"
description: "Calculates a percentile based on entire data set."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# Percentile_Disc (Azure Stream Analytics)
Calculates a percentile based on entire data set. For a given percentile value P, PERCENTILE_DISC sorts the values of the expression in the ORDER BY clause and returns the value within the smallest cumulative distance that is greater than or equal to P. For example, PERCENTILE_DISC (0.5) will compute the 50th percentile (that is, the median) of an expression. PERCENTILE_DISC calculates the percentile based on a discrete distribution of the data values; the result is equal to a specific value from the input data.
  
 ## Syntax  
  
```SQL   
PERCENTILE_DISC ( numeric_literal )
       OVER ( ORDER_BY order_by_expression [ ASC | DESC ])
```  
  
## Arguments  
 **numeric_literal**  
  
The percentile to compute. The value must range between 0 and 1.  

 **OVER ( ORDER BY order_by_expression [ ASC | DESC] )**

Specifies a list of numeric values to sort and compute percentile over. Only one order_by_expression is allowed. The expression must evaluate to a numeric type. Other data types are not allowed. The default sort order is ascending.

## Return Types  

The return type is determined by the order_by_expression type.
  
## Examples  

The following example uses PERCENTILE_DISC to find the 95th percentile of service availability across regions. Note that the function will always return a percentile that is within the input data set.
  
```SQL  
SELECT PERCENTILE_DISC(0.95) OVER (ORDER BY serviceAvailability)
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

0.99
