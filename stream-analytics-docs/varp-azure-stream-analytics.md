---
title: "VARP"
description: "Returns the statistical variance for the population for all values in a group. Null values are ignored.  "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# VARP
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

  Returns the statistical variance for the population for all values in a group. Null values are ignored.  
  
 ## Syntax  
  
```SQL   
VARP (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. VARP can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, VARP (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
