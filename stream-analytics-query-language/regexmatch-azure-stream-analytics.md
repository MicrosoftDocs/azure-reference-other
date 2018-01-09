---
title: "REGEXMATCH (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-06-15"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 1b3a8da3-812a-451d-b052-cd02f1962035
caps.latest.revision: 7
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
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
  
  