---
title: "YEAR"
description: "Returns an integer that represents the year of the specified date."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# YEAR
  Returns an integer that represents the year of the specified date  
  
 ## Syntax  
  
```SQL   
YEAR ( date )  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT YEAR (EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  
