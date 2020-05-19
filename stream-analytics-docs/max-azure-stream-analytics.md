---
title: "MAX (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the maximum value in the expression.  "
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea


ms.service: stream-analytics
ms.topic: reference
ms.assetid: eb36fa10-c917-4817-a3d1-ece443ab663c
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# MAX (Azure Stream Analytics)
  Returns the maximum value in the expression.  
  
 ## Syntax  
  
```SQL   
-- Aggregate Function Syntax
MAX ( expression )  

-- Analytic Function Syntax
MAX ( expression ) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
```  
  
## Arguments  
**expression**  
  
Is a constant, column name, or function, and any combination of arithmetic operators. MAX can be used with bigint and float columns, but not with bit columns. Aggregate functions and subqueries are not permitted.  
  
**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

Determines the group of rows over which MAX is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Return Types  
 Returns a value same as expression.  
  
## General Remarks  
 If payload schema was not defined with CREATE TABLE statement and type of the result expression is unknown at query compilation time, return value will have float type.  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, MAX (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
```  
  
## See Also
[GROUP BY clause](group-by-azure-stream-analytics.md)   
[OVER clause](over-azure-stream-analytics.md)