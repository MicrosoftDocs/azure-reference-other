---
title: "AVG (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: c0638288-6ca0-49f7-b119-8c0af842203a
caps.latest.revision: 5
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# AVG (Azure Stream Analytics)
  Returns the average of the values in a group. Null values are ignored.  
  
 **Syntax**  
  
```  
AVG (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. AVG can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 The return type is determined by the type of the evaluated result of expression.  
  
## Examples  
  
```SQL
SELECT System.TimeStamp AS OutTime, TollId, AVG (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  