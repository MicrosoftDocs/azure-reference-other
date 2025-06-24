---
title: "SUM"
description: "Returns the sum of all the values in the expression. SUM can be used with numeric columns only."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# SUM
  Returns the sum of all the values in the expression. SUM can be used with numeric columns only. NULL values are ignored. For all NULL values the result is also NULL.
  
 ## Syntax  
  
```SQL   
-- Aggregate Function Syntax
SUM ( expression )  

-- Analytic Function Syntax
SUM ( expression ) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
```  
  
## Arguments  
**expression**  
  
Is a constant, column, or function, and any combination of arithmetic operators. SUM can be used with bigint and float columns.  
  
**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

Determines the group of rows over which SUM is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Return Types  
 Returns the summation of all expression values in the most precise expression data type.  
  
## Example  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, SUM (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
```

## See Also
[GROUP BY clause](group-by-azure-stream-analytics.md)   
[OVER clause](over-azure-stream-analytics.md)
