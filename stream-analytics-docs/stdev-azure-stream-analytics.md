---
title: "STDEV"
description: "Returns the statistical standard deviation of all values in a group. Null values are ignored. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# STDEV
  Returns the statistical standard deviation of all values in a group. Null values are ignored.  
  
 ## Syntax  
  
```SQL   
STDEV (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. STDEV can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, STDEV (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
