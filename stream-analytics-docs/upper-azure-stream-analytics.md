---
title: "UPPER (Azure Stream Analytics)"
description: "Returns a character expression with lowercase character data converted to uppercase. "
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# UPPER (Azure Stream Analytics)
  Returns a character expression with lowercase character data converted to uppercase.  
  
 ## Syntax  
  
```SQL   
UPPER ( string_expression )  
```  
  
## Arguments  
 **string_expression**  
  
 Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max)  
  
## Return Types  
 nvarchar(max)  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, UPPER(LicensePlate) AS LicensePlate_Upper  
FROM Input  
```  
  
## See Also  
 [LOWER &#40;Azure Stream Analytics&#41;](lower-azure-stream-analytics.md)  
  
  
