---
title: "LEN (Azure Stream Analytics) | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 82f25a01-f71c-470a-9b01-93fc374fda90
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# LEN (Azure Stream Analytics)
  Returns the number of characters of the specified string expression, excluding trailing blanks.  
  
 **Syntax**  
  
```  
LEN ( string_expression )  
  
```  
  
## Arguments  
 **string_expression**  
  
 Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max)  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, LicensePlate, LEN (LicensePlate) AS Len_License  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
```  
  
  