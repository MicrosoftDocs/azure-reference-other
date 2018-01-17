---
title: "VAR (Azure Stream Analytics) | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 1bd52a25-c32e-47ac-84d7-21255ae8d572
caps.latest.revision: 5
ms.workload: data-services
ms.date: 22/04/2016
ms.author: sngun
---
# VAR (Azure Stream Analytics)
  Returns the statistical variance of all values in a group. Null values are ignored.  
  
 **Syntax**  
  
```  
VAR (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. VAR can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```SQL  
SELECT System.TimeStamp AS OutTime, TollId, VAR (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  