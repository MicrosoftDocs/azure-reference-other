---
title: "SUM (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 74d404e3-4a67-4303-b95e-d7063af3c513
caps.latest.revision: 5
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# SUM (Azure Stream Analytics)
  Returns the sum of all the values in the expression. SUM can be used with numeric columns only. Null values are ignored.  
  
 **Syntax**  
  
```  
SUM ( expression )  
```  
  
## Arguments  
 **expression**  
  
 Is a constant, column, or function, and any combination of arithmetic operators. SUM can be used with bigint and float columns.  
  
## Return Types  
 Returns the summation of all expression values in the most precise expression data type.  
  
## Example  
  
```  
SELECT System.TimeStamp AS OutTime, TollId, SUM (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  