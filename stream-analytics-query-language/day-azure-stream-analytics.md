---
title: "DAY (Azure Stream Analytics) | Microsoft Docs"
description: "Returns an integer representing the day (day of the month) of the specified date."
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 0ffa3e9c-6bf4-4d46-ad0b-228d6125c5c5
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: jasonh
---
# DAY (Azure Stream Analytics)
  Returns an integer representing the day (day of the month) of the specified date.  
  
 **Syntax**  
  
```  
DAY ( date )  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT DAY (EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
