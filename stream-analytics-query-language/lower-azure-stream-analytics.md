---
title: "LOWER (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 378b640d-7cd8-429a-83f8-7738c008411d
caps.latest.revision: 6
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# LOWER (Azure Stream Analytics)
  Returns a character expression after converting uppercase character data to lowercase.  
  
 **Syntax**  
  
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
  
  