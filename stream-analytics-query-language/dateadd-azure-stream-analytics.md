---
title: "DATEADD (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 1dc4c848-7cf1-4f7a-ae5b-311f9021eea2
caps.latest.revision: 8
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# DATEADD (Azure Stream Analytics)
  Returns a specified date with the specified number interval (signed integer) added to a specified datepart of that date.  
  
 **Syntax**  
  
```  
DATEADD ( datepart , number, date )  
```  
  
## Arguments  
 **datepart**  
  
 Is the part of startdate and enddate that specifies the type boundary crossed. The following table lists all valid datepart arguments.  
  
|datepart|Abbreviations|  
|--------------|-------------------|  
|year|yy, yyyy|  
|quarter|qq, q|  
|month|mm, m|  
|dayofyear|dy, y|  
|day|dd, d|  
|week|wk, ww|  
|weekday|dw, w|  
|hour|hh|  
|minute|mi, n|  
|second|ss, s|  
|millisecond|ms|  
|microsecond|mcs|  
  
 **number**  
  
 Is an expression that can be resolved to a bigint that is added to a datepart of date. If you specify a value with a decimal fraction, the fraction is truncated and not rounded  
  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression,  or string literal  
  
## Return Types  
 bigint  
  
## Examples  
  
```  
SELECT DATEDIFF (minute, EntryTime, DATEADD(hour,2,EntryTime)) AS DiffTime  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  