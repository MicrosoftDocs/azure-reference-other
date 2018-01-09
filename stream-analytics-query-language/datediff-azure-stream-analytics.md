---
title: "DATEDIFF (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: e8f6ec67-f286-4fa5-8acf-ae7c179d8b19
caps.latest.revision: 9
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# DATEDIFF (Azure Stream Analytics)
  Returns the count (signed integer) of the specified datepart boundaries crossed between the specified startdate and enddate.  
  
 **Syntax**  
  
```  
DATEDIFF ( datepart , startdate, enddate )  
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
  
 **startdate**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal. Startdate  is substructed from enddate  
  
 **enddate**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal. Startdate  is substructed from enddate  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT DATEDIFF (minute, EntryTime, CAST(’2014-09-10 12:00:00’ AS datetime)) AS DiffTime  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
```SQL  
SELECT DATEDIFF (minute, EntryTime, DATEADD(hour,2,EntryTime)) AS DiffTime  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
> [!NOTE]  
>  In Stream Analytics Query Language there is a special use of DATEDIFF function when used inside a JOIN condition. See [JOIN &#40;Azure Stream Analytics&#41;](join-azure-stream-analytics.md).  
  
  