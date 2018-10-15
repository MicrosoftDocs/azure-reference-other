---
title: "SUM (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the sum of all the values in the expression. SUM can be used with numeric columns only."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 74d404e3-4a67-4303-b95e-d7063af3c513
caps.latest.revision: 5
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# SUM (Azure Stream Analytics)
  Returns the sum of all the values in the expression. SUM can be used with numeric columns only. Null values are ignored.  
  
 ## Syntax  
  
```  
SUM ( expression )  
```  
  
## Arguments  
 **expression**  
  
 Is a constant, column, or function, and any combination of arithmetic operators. SUM can be used with bigint and float columns.  
  
## Return Types  
 Returns the summation of all expression values in the most precise expression data type.  
  
## Example  
  
```SQL  
SELECT System.TimeStamp AS OutTime, TollId, SUM (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
