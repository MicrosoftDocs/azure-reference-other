---
title: "LOWER"
description: "Returns a character expression after converting uppercase character data to lowercase."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# LOWER
  Returns a character expression after converting uppercase character data to lowercase.  
  
 ## Syntax  
  
```SQL   
LOWER ( string_expression )  
```  
  
## Arguments  
 **string_expression**  
  
 Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max)  
  
## Return Types  
 nvarchar(max)  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, LOWER(LicensePlate) AS LicensePlate_Lower  
FROM Input  
```  
  
## See Also  
 [UPPER &#40;Azure Stream Analytics&#41;](upper-azure-stream-analytics.md)  
  
  
