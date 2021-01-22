---
title: "MIN (Azure Stream Analytics)"
description: "Returns the minimum value in the expression."
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 04/22/2016
---
# MIN (Azure Stream Analytics)
  Returns the minimum value in the expression.  
  
 ## Syntax  
  
```SQL   
-- Aggregate Function Syntax
MIN ( expression )  

-- Analytic Function Syntax
MIN ( expression ) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
```  
  
## Arguments  
**expression**  
  
Is a constant, column name, or function, and any combination of arithmetic operators. MIN can be used with bigint and float columns. Aggregate functions and subqueries are not permitted.  
  
**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

Determines the group of rows over which MIN is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Return Types  
 Returns a value same as expression.  
  
## General Remarks  
 If payload schema was not defined with CREATE TABLE statement and type of the result expression is unknown at query compilation time, return value will have float type.  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, MIN (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
```  
  
## See Also
[GROUP BY clause](group-by-azure-stream-analytics.md)   
[OVER clause](over-azure-stream-analytics.md)