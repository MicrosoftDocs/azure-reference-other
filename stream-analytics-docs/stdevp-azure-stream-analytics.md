---
title: "STDEVP (Azure Stream Analytics)"
description: "Returns the statistical standard deviation for the population for all values in a group. Null values are ignored."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# STDEVP (Azure Stream Analytics)
  Returns the statistical standard deviation for the population for all values in a group. Null values are ignored.  
  
 ## Syntax  
  
```SQL   
STDEVP (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. STDEVP can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, STDEVP (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
