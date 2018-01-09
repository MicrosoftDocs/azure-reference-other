---
title: "DATEPART (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: d8aa30a4-2cf4-4b4f-ac5c-8204a72abb7a
caps.latest.revision: 8
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
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
  
  