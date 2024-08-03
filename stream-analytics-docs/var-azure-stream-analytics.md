---
title: "VAR (Azure Stream Analytics)"
description: "Returns the statistical variance of all values in a group."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# VAR (Azure Stream Analytics)
  Returns the statistical variance of all values in a group. Null values are ignored.  
  
 ## Syntax  
  
```SQL   
VAR (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. VAR can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, VAR (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
