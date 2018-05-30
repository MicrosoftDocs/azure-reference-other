---
title: "DATEADD (Azure Stream Analytics) | Microsoft Docs"
description: "Returns a specified date with the specified number interval (signed integer) added to a specified datepart of that date."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 1dc4c848-7cf1-4f7a-ae5b-311f9021eea2
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
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
  
```SQL  
SELECT DATEADD(hour,2,EntryTime) AS TimeAddedHours
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
