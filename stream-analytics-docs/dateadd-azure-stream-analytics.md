---
title: "DATEADD (Azure Stream Analytics)"
description: "Returns a specified date with the specified number interval (signed integer) added to a specified datepart of that date."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# DATEADD (Azure Stream Analytics)
  Returns a specified date with the specified number interval (signed integer) added to a specified datepart of that date.  
  
 ## Syntax  
  
```SQL   
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
SELECT DATEADD(hour,2,EntryTime) AS AdjustedTime
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
