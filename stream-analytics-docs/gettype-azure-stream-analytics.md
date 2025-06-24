---
title: "GetType"
description: "Returns a data type name of the value.  "
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# GetType
  Returns a data type name of the value.  
  
 ## Syntax  
  
```SQL   
GetType (expression)  
  
```  
  
## Arguments  
 **expression**  
  
 Is any valid expression.  
  
## Return Types  
 Returns data type name of the expression. The type of the returned name is nvarchar(max). Please see all supported data types in [Data Types](data-types-azure-stream-analytics.md).  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime   
FROM Input  
WHERE GetType( EntryTime ) = 'datetime'
```  
  
  
