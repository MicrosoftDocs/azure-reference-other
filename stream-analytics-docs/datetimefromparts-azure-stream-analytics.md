---
title: "DATETIMEFROMPARTS"
description: " Returns a datetime value for the specified date and time. "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# DATETIMEFROMPARTS
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

  Returns a datetime value for the specified date and time.  
  
 ## Syntax  
  
```SQL   
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
  
  
