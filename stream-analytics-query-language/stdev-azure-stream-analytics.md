---
title: "STDEV (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 6a0dadc8-8d6b-422a-a096-7a2176b6ac79
caps.latest.revision: 5
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# STDEV (Azure Stream Analytics)
  Returns the statistical standard deviation of all values in a group. Null values are ignored.  
  
 **Syntax**  
  
```  
STDEV (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. STDEV can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```SQL  
SELECT System.TimeStamp AS OutTime, TollId, STDEV (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  