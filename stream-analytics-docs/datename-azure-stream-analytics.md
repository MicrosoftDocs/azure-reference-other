---
title: "DATENAME (Azure Stream Analytics)"
description: "Returns a character string that represents the specified datepart of the specified date."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# DATENAME (Azure Stream Analytics)
  Returns a character string that represents the specified datepart of the specified date.  
  
 ## Syntax  
  
```SQL   
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
  
  
