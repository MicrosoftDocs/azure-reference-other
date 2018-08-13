---
title: "DATETIMEFROMPARTS (Azure Stream Analytics) | Microsoft Docs"
description: " Returns a datetime value for the specified date and time. "
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 6e69e0ea-6774-4ad2-981b-a4624a56c52b
caps.latest.revision: 5
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# DATETIMEFROMPARTS (Azure Stream Analytics)
  Returns a datetime value for the specified date and time.  
  
 **Syntax**  
  
```  
DATETIMEFROMPARTS (year, month, day, hour, minute, seconds, milliseconds)  
  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 datetime  
  
## Examples  
  
```SQL 
SELECT EntryTime, DATETIMEFROMPARTS(2014,9,10,12,DATEPART(minute,EntryTime)+10,00,00)   
AS ExitTime  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
