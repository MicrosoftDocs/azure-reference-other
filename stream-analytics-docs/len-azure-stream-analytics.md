---
title: "LEN"
description: "Returns the number of characters of the specified string expression, excluding trailing blanks."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# LEN
  Returns the number of characters of the specified string expression, excluding trailing blanks.  
  
 ## Syntax  
  
```SQL   
LEN ( string_expression )  
  
```  
  
## Arguments  
 **string_expression**  
  
 Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max)  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, LicensePlate, LEN (LicensePlate) AS Len_License  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
```  
  
  
