---
title: "STDEVP (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 6d8c33cc-5087-43e9-b4de-e7e120dbb1a7
caps.latest.revision: 5
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# STDEVP (Azure Stream Analytics)
  Returns the statistical standard deviation for the population for all values in a group. Null values are ignored.  
  
 **Syntax**  
  
```  
STDEVP (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. STDEVP can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 float  
  
## Examples  
  
```  
SELECT System.TimeStamp AS OutTime, TollId, STDEVP (Toll)   
FROM Input  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  