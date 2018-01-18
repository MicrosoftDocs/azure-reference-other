---
title: "DATENAME (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 0b865481-1a9c-405f-9eeb-6d80dde0731a
caps.latest.revision: 8
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# DATENAME (Azure Stream Analytics)
  Returns a character string that represents the specified datepart of the specified date.  
  
 **Syntax**  
  
```  
DATENAME ( datepart , date )  
```  
  
## Arguments  
 **datepart**  
  
 Is any valid expression.  
  
 **data_type**  
  
 Is the part of the date to return. The following table lists all valid datepart arguments.  
  
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
 nvarchar(max)  
  
## Examples  
  
```SQL  
SELECT DATENAME (month, EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  