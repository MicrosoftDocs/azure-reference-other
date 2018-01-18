---
title: "MAX (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: eb36fa10-c917-4817-a3d1-ece443ab663c
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# MAX (Azure Stream Analytics)
  Returns the maximum value in the expression.  
  
 **Syntax**  
  
```  
MAX ( expression )  
```  
  
## Arguments  
 **expression**  
  
 Is a constant, column name, or function, and any combination of arithmetic operators. MAX can be used with bigint and float columns, but not with bit columns. Aggregate functions and subqueries are not permitted.  
  
## Return Types  
 Returns a value same as expression.  
  
## General Remarks  
 If payload schema was not defined with CREATE TABLE statement and type of the result expression is unknown at query compilation time, return value will have float type.  
  
## Examples  
  
```SQL  
  
SELECT System.TimeStamp AS OutTime, TollId, MAX (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  