---
title: "DAY (Azure Stream Analytics)"
description: "Returns an integer representing the day (day of the month) of the specified date."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# DAY (Azure Stream Analytics)
  Returns an integer representing the day (day of the month) of the specified date.  
  
 ## Syntax  
  
```SQL   
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
  
  
