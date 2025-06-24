---
title: "REGEXMATCH"
description: "Returns the starting position of the first occurrence of a pattern in a specified expression, or 0 if the pattern is not found, on all valid nvarchar(max) data types."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# REGEXMATCH
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Returns the starting position of the first occurrence of a pattern in a specified expression, or 0 if the pattern is not found, on all valid nvarchar(max) data types. Pattern is interpreted as single-line, case-insensitive, ECMAScript compatible regular expression.  
  
 ## Syntax  
  
```SQL   
REGEXMATCH( <expression>, <pattern> )  
```  
  
## Arguments  
 **expression**  
  
 An expression, typically a column that is searched for the specified pattern. Where the expression is of the nvarchar(max) data type.  
  
 **pattern**  
  
 A character expression that contains the regular expression to be found.  
  
## Return Types  
 bigint  
  
## Remarks  
 If either pattern or expression is NULL, REGEXMATCH returns NULL.  
  
 If pattern is invalid regular expression, REGEXMATCH returns 0.  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, LicensePlate, REGEXMATCH( LicensePlate, '[0-9][0-9][0-9]' ),  
FROM Input TIMESTAMP BY EntryTime  
```  
  
  
