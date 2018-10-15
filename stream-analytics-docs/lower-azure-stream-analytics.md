---
title: "LOWER (Azure Stream Analytics) | Microsoft Docs"
description: "Returns a character expression after converting uppercase character data to lowercase."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 378b640d-7cd8-429a-83f8-7738c008411d
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# LOWER (Azure Stream Analytics)
  Returns a character expression after converting uppercase character data to lowercase.  
  
 ## Syntax  
  
```  
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
  
  
