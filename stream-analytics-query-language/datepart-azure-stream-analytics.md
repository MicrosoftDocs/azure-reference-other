---
title: "DATEPART (Azure Stream Analytics) | Microsoft Docs"
description: "Returns an integer that represents the specified datepart of the specified date.  "
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: d8aa30a4-2cf4-4b4f-ac5c-8204a72abb7a
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: jasonh
---
# DATEPART (Azure Stream Analytics)
  Returns an integer that represents the specified datepart of the specified date.  
  
 **Syntax**  
  
```  
DATEPART ( datepart , date )  
```  
  
## Arguments  
 **datepart**  
  
 Is the part of date (a date or time value) for which an integer will be returned. The following table lists all valid datepart arguments.  
  
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
  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT DATEPART (weekday, EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
