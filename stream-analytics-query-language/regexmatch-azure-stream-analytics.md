---
title: "REGEXMATCH (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the starting position of the first occurrence of a pattern in a specified expression, or 0 if the pattern is not found, on all valid nvarchar(max) data types."
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 1b3a8da3-812a-451d-b052-cd02f1962035
caps.latest.revision: 7
ms.workload: data-services
ms.date: 06/15/2016
ms.author: jasonh
---
# REGEXMATCH (Azure Stream Analytics)
  Returns the starting position of the first occurrence of a pattern in a specified expression, or 0 if the pattern is not found, on all valid nvarchar(max) data types. Pattern is interpreted as single-line, case-insensitive, ECMAScript compatible regular expression.  
  
 **Syntax**  
  
```  
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
  
  
