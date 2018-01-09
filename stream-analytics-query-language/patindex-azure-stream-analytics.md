---
title: "PATINDEX (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 42e4e849-2fbd-4374-bd8c-d40130ae81a3
caps.latest.revision: 7
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# PATINDEX (Azure Stream Analytics)
  Returns the starting position of the first occurrence of a pattern in a specified expression, or 0 if the pattern is not found, on all valid nvarchar(max) data types.  
  
 **Syntax**  
  
```  
PATINDEX ( '%pattern%' , expression )  
```  
  
## Arguments  
 **pattern**  
  
 A character expression that contains the sequence to be found. Wildcard characters can be used; however, the % character must come before and follow pattern (except when searching for first or last characters). pattern is an expression of the character string data type category. pattern is limited to 8000 characters.  
  
 **expression**  
  
 An expression, typically a column that is searched for the specified pattern. Where the expression is of the nvarchar(max) data type.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, LicensePlate, PATINDEX ( ‘%100%’,LicensePlate ),  
FROM Input TIMESTAMP BY EntryTime  
  
```  
  
  