---
title: "MONTH (Azure Stream Analytics)"
description: "Returns an integer that represents the month of the specified date."
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 04/22/2016
---
# MONTH (Azure Stream Analytics)
  Returns an integer that represents the month of the specified date.  
  
 ## Syntax  
  
```SQL   
MONTH ( date )  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT MONTH (EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
