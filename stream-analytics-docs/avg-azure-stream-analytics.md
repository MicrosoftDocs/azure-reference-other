---
title: "AVG (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the average of the values in a group. Null values are ignored."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: c0638288-6ca0-49f7-b119-8c0af842203a
caps.latest.revision: 5
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---

# AVG (Azure Stream Analytics)
  Returns the average of the values in a group. Null values are ignored.  
  
 ## Syntax  
  
```SQL   
-- Aggregate Function Syntax
AVG (expression )  

-- Analytic Function Syntax
AVG ( expression ) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
```  
  
## Arguments  
**expression**  
  
Is an expression of the exact numeric or approximate numeric data type category. AVG can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

Determines the group of rows over which AVG is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Return Types  
 The return type is determined by the type of the evaluated result of expression.  
  
## Examples  
  
```SQL
SELECT System.Timestamp() AS OutTime, TollId, AVG (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
```  
  
## See Also
[GROUP BY clause](group-by-azure-stream-analytics.md)   
[OVER clause](over-azure-stream-analytics.md)
  
