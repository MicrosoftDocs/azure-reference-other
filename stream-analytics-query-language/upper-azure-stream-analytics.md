---
title: "UPPER (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 36eeda67-4fe9-46ff-b5cb-5a53244f3ed3
caps.latest.revision: 6
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# UPPER (Azure Stream Analytics)
  Returns a character expression with lowercase character data converted to uppercase.  
  
 **Syntax**  
  
```  
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
  
  